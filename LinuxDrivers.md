# Some driver code examples #



## Accessing the ARM PMU via a kernel module ##

```
///////////////////////////////////////////
// Performance counter driver
// /////////////////////////////////////////

#include <linux/module.h>
#include <linux/init.h>
#include <linux/fs.h>
#include <linux/cdev.h>
#include <linux/device.h>
//#include <asm/uaccess.h> //get_user, put_user
#include "perf_driver.h"

static int my_open(struct inode *inode, struct file *file);
static int my_close(struct inode *inode, struct file *file);
static int my_ioctl(struct inode *inode, struct file *file, unsigned int cmd, unsigned long arg);


dev_t g_dev_node;
static struct cdev * g_cdev = NULL;
static struct file_operations g_fops = {
    .owner = THIS_MODULE,
    .open = my_open,
    .release = my_close,

    .ioctl = my_ioctl,

};
static struct class * g_perf_class = NULL;

void prfcmt_start(void);
int prfcmt_read(void);
void prfcmt_stop(void);
void prfcmt_clear(void);


static int __init my_init(void)
{

    if (alloc_chrdev_region ( &g_dev_node,
                              0, //first minor
                              1, //how many minors are needed.
                              "perf_char") < 0){ //As it will appear under /proc/devices
        printk(KERN_ERR "Failed to get a major device node\n");
        return -1;
    }

    printk("perf_char: Got Major %d\n", MAJOR(g_dev_node));

    //Now let? create the char dev.
    g_cdev = cdev_alloc();
    cdev_init(g_cdev, &g_fops);
    cdev_add(g_cdev, g_dev_node, 1);

    //Now that the device has been created we can create the inode
    //using udev.
    g_perf_class = class_create(THIS_MODULE, "perf_char");
    device_create(g_perf_class,
                        NULL, //No parent class
                        g_dev_node,
                        NULL, //No real device. This is a fake driver.
                        "%s", "perf_char"); //It will appear as /dev/perf_char.

    printk("successfully created /dev/perf_char\n");
    return 0;
}

static void __exit my_exit(void)
{
    device_destroy(g_perf_class, g_dev_node);
    class_destroy(g_perf_class);
    cdev_del(g_cdev);
    unregister_chrdev_region ( g_dev_node, 1);
    printk("Good Bye from perf\n");
}

static int my_open(struct inode *inode, struct file *file)
{
    printk("Somebody opened me!\n");
    return 0;
}

static int my_close(struct inode *inode, struct file *file)
{
    printk("Somebody closed me!\n");
    return 0;
}

//This is non standard. this function will basically assume "cmd" is a position in
// a char ptr pointed by arg. The character in that position will be converted to lowercase
// if it? uppercase, will be uppercase if it? lowercase
static int my_ioctl(struct inode *inode, struct file *file, unsigned int cmd, unsigned long arg)
{
    //printk("my_ioctl, cmd=%u, arg_dec=%lu, arg_hex=0x%08lX\n", cmd, arg, arg);

    switch (cmd){
        case CMD_START:
		prfcmt_start();
	return 0;
	case CMD_READ:
	return prfcmt_read();
	case CMD_STOP:
		prfcmt_stop();
	return 0;
	case CMD_CLEAR:
		prfcmt_clear();
	return 0;
	default:
		printk(KERN_ERR "Unknown command %u\n", cmd);
	return -1;
    }

    return -1;
}

module_init(my_init);
module_exit(my_exit);

MODULE_LICENSE("GPL");
MODULE_AUTHOR("Me");
MODULE_DESCRIPTION("Measure the performance");
MODULE_VERSION("1.0");
```