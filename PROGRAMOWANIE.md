III. FUNKCJE

Zad. 1. Napisz funkcję obliczającą pole kuli o podanym promieniu.
```c
#include <stdio.h>
#include <math.h>
double poleKuli(double r)
{
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
#include <stdio.h>
#include <ctype.h>
#define MAX 32
int main(){
 char napis[MAX];
	int c, i=0, end;
	puts ("Wpisz dowolny tekst: ");
	while ((c=getchar())!=EOF)
	{
		napis[i]=toupper(c);
		i++;
	}
	end=--i;
	for (i=0; i<=end; i++)
		printf ("%c", napis[i]); 
	getchar ();                 
	return 0;                 
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
double potega(double a, int n)
{
	int i;
	double x=1.0;
	for(i=1;i<=n;i++)
	{
		x=x*a;
	}
	return x;
}
```
Zad. 4. Napisz funkcję obliczającą pierwiastek z a algorytmem Herona.
```c
#include <stdio.h>
#include <math.h>
double Heron (double a)
{
 double x=1, eps=1e-15;
	do
	{
		x=0.5*(x+(a/x));
	}
	while (fabs(x-a/x)>eps*x);
	return x;
}
int main(){
	double a;
	double x=1;
	double z;
	printf ("Podaj liczbe: ");
	scanf ("%lf", &a);
	for (z=1e-5; z<=1e15; z=z*10)
	{
		printf ("\nHeron(%lf)=%.15lf\n", z, Heron(a));
		printf ("\nsqrt(%lf)=%.15lf\t", z, sqrt(a));
		printf ("\n\nblad wzgledny=%.15le", (Heron(a)-sqrt(a))/sqrt(a));
		getchar ();
		getchar ();
		return 0;
	}
}
```
Zad. 5. Napisz funkcje do szybkiego obliczania a^n.
```c
#include <stdio.h>
int potegaAn (int a, int n);
int main (){
 int a, p, n;
	printf ("Podaj liczbe naturalna: ");
	scanf ("%d", &a);
	printf ("\nPodaj wykladnik (liczba naturalna): ");
	scanf ("%d", &n);
	p = potegaAn (a, n);
	printf ("\nWartosc %d do potegi %d wynosi %d", a, n, p);
	getchar ();
	getchar ();
	return 0;
}
int
	potegaAn (int a, int n)
{
	int i = n, p = 1, q = a;
	while (i > 0)
	{
		if (i % 2 != 0)
			p = p * q;
		q = q * q;
		i = i / 2;
	}
	return p;
}
```
Zad. 6. Napisz funkcje do szybkiego obliczania a^n (n-liczba cakowita, a-typ double).
```c
#include <stdio.h>
double potegaAn (double a, int n);
int main () {
 int n;
	double a, p;
	printf ("\nPodaj liczbe: ");
	scanf ("%lf", &a);
	printf ("\nPodaj wykladnik (liczba naturalna): ");
	scanf ("%d", &n);
	p = potegaAn (a, n);
	printf ("\nWartosc %lf do potegi %d wynosi %lf", a, n, p);
	getchar ();
	getchar ();
	return 0;
}
double potegaAn (double a, int n)
{
	int i = n, minus = 0;
	double p = 1.0, q = a;
	if (i < 0)
	{
		minus = 1;
		i = -i;
	}
	while (i > 0)
	{
		if (i % 2 != 0)
			p = p * q;
		q = q * q;
		i = i / 2;
	}
	if (minus == 0)
		return p;
	else
		return (1.0 / p);
}
```

IV. TABLICE

Zad. 1. Wypisz wszystkie elementy tablicy: int dane[]={-44, 5, 67, -2, 0, 33, 77} w kolejności od pierwszego do ostatniego i odwrotnie.
```c

```
Zad. 2. Napisz program, który podany tekst wyświetli wielkimi literami.
```c

```
