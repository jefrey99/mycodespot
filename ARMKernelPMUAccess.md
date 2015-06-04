# How to build an ARM/linux kernel to access the PMU registers #

There is some plumbing to do, in that you need to wire up the PMU interrupts in the bsp part of the kernel:

```
arch/arm/mach-vexpress/ct-ca9x4.c
```

```
static struct resource pmu_resources[] = {
        [0] = {
                .start  = IRQ_CT_CA9X4_PMU_CPU0,
                .end    = IRQ_CT_CA9X4_PMU_CPU0,
                .flags  = IORESOURCE_IRQ,
        },
        [1] = {
                .start  = IRQ_CT_CA9X4_PMU_CPU1,
                .end    = IRQ_CT_CA9X4_PMU_CPU1,
                .flags  = IORESOURCE_IRQ,
        },
        [2] = {
                .start  = IRQ_CT_CA9X4_PMU_CPU2,
                .end    = IRQ_CT_CA9X4_PMU_CPU2,
                .flags  = IORESOURCE_IRQ,
        },
        [3] = {
                .start  = IRQ_CT_CA9X4_PMU_CPU3,
                .end    = IRQ_CT_CA9X4_PMU_CPU3,
                .flags  = IORESOURCE_IRQ,
        },
};

static struct platform_device pmu_device = {
        .name           = "arm-pmu",
        .id             = ARM_PMU_DEVICE_CPU,
        .num_resources  = ARRAY_SIZE(pmu_resources),
        .resource       = pmu_resources,
};

```

# More Details To Come #


![http://chart.apis.google.com/chart?chs=200x125&chd=t:10,20,30,40|83.18,18.73,12.04&cht=bvg&nonsense=jeff.png](http://chart.apis.google.com/chart?chs=200x125&chd=t:10,20,30,40|83.18,18.73,12.04&cht=bvg&nonsense=jeff.png)



![http://www.arm.com/images/site/arm_logo.gif](http://www.arm.com/images/site/arm_logo.gif)
![http://www.ece.nmsu.edu/~jeastlac/images/penguin_small.jpg](http://www.ece.nmsu.edu/~jeastlac/images/penguin_small.jpg)