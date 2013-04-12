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
Zad. 3. Napisz funkcję obliczającą a^n (n-liczba naturalna) za pomocą pętli.
```c
#include <stdio.h>
#include <math.h>
double potega(double a, int n);
int main() {
double a;
int n;
double x;
printf("Podaj liczbe: ");
scanf("%lf",&a);
printf("\nPodaj wykladnik (liczba naturalna): ");
scanf("%d",&n);
x=potega(a,n);
printf("\n%.3lf do potegi %d rowna sie %.3lf ", a, n, x);
getchar();
getchar();
return 0;
}   
double potega(double a, int n) {
int i;
double x=1.0;
for(i=1;i<=n;i++){
x=x*a;
}
return x;
}
```
