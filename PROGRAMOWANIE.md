# JEZYKI PROGRAMOWANIA

FUNKCJE

Zad. 1. Napisz funkcję obliczającą pole kuli o podanym promieniu.
```c
#include <stdio.h>
#include <math.h>
double poleKuli(double r){
return  4*M_PI*r*r;   
}
int main(){
double r;     
printf ("Podaj promien kuli: ");
scanf ("%lf", &r);
printf ("\nP = %d x %.3lf x %.0lf x %.0lf = %.3lf\n", 4, M_PI, r, r, poleKuli(r));
getchar ();
getchar ();
return 0;
}
```
