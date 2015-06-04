# OpenMP Code Snippets - Stolen from T. Sterling #

### In case you forgot the GCC compile commands ###

```
$ gcc -fopenmp -o executable ompfile.c
```
## Multi threaded Hello World with OpenMP ##

```
#include <stdio.h>
#include <omp.h>
main () 
{
int nthreads, tid;

#pragma omp parallel private(nthreads, tid)
{
  tid = omp_get_thread_num();
  if (tid == 0) {
      nthreads = omp_get_num_threads();
      printf("Number of cores = %d\n", nthreads);
  }
  printf("Hello World from core = %d\n", tid);
}
}

```
## Multi Treaded Computation of the dot product ##
```
#include <omp.h>
#include <stdio.h>
main () {
int i, n, chunk;
float a[4], b[4], result;
n = 4;
chunk = 2;
result = 0.0;
for (i=0; i < n; i++)
 {
a[i] = i * 1.0;
b[i] = i * 2.0;
}
#pragma omp parallel for default(shared) private(i) schedule(static,chunk) reduction(+:result)
for (i=0; i < n; i++)
result = result + (a[i] * b[i]);
printf(" a[i] b[i] a[i]*b[i]\n");
for (i=0; i<n; i++)
printf(" %f %f %f\n", a[i], b[i], a[i]*b[i]);
printf("Final result= %f\n",result);
 }
```


## Multi Theaded Computation of Simpsons Rule using OpenMP ##
```
#include<stdio.h>
#include <omp.h>
#include <time.h>

void main()
{
   float x[20],y[20],ans;
   int i,npnt,h;

   // To access CPU time
   clock_t start, end;
   double cpu_time_used;


   printf("Enter number of points(max 20):\n");
   scanf("%d",&npnt);
   if(npnt%2==0)
   {
     printf("Number of points must be odd\n");
     getchar();
     return;
   }

   for(i=0;i<npnt;i++)
   {
     printf("Enter Value of x[%d] and y[%d]:\n",i,i);
     scanf("%f %f",&x[i],&y[i]);
   }
   h=x[1]-x[0];
   ans=y[0];
   start = clock();

#pragma omp parallel for reduction(+:ans)
   for(i=1;i<npnt-1;i++)
   {
     if(i%2==1)
       ans=ans+4*y[i];
     else
       ans=ans+2*y[i];
   }
   ans=(ans+y[npnt-1])*h/3;
   end = clock();
   cpu_time_used = (end - start) / ((double) CLOCKS_PER_SEC);

   printf("\n==================\n");
   printf(" CPU time: %.4lf\n",cpu_time_used);
   printf(" Answer=%.2f\n",ans);
   printf("===================\n");
   getchar();    
}

```