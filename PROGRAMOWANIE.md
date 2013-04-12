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
Zad. 2. Napisz funkcję wartoscBezwzgledna zwracająca wartość bezwzględną z liczby całkowitej.
```c
# include <stdio.h>
# include <math.h>
int wartoscBezwzgledna(int x){
if (x<=0) return -x;
else return x;
}
int main (){
int x;
printf ("Podaj liczbe: ");
scanf ("%d", &x);
printf ("\nWARTOSC BEZWZGLEDNA TO %d", wartoscBezwzgledna(x));
getchar ();
getchar ();
}
```
