_**III. FUNKCJE**_

**Zad. 1.** Napisz funkcję obliczającą pole kuli o podanym promieniu.
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
**Zad. 2.** Napisz funkcję wartoscBezwzgledna zwracająca wartość bezwzględną z liczby całkowitej.
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
**Zad. 3.** Napisz funkcję obliczającą a^n (n-liczba naturalna) za pomocą pętli.
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
**Zad. 4.** Napisz funkcję obliczającą pierwiastek z a algorytmem Herona.
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
**Zad. 5.** Napisz funkcje do szybkiego obliczania a^n.
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
**Zad. 6.** Napisz funkcje do szybkiego obliczania a^n (n-liczba cakowita, a-typ double).
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

_**IV. TABLICE**_

**Zad. 1.** Wypisz wszystkie elementy tablicy: int dane[]={-44, 5, 67, -2, 0, 33, 77} w kolejności od pierwszego do ostatniego i odwrotnie.
```c
#include <stdio.h>
#include <math.h>
int main (){
	int dane[]={-44, 5, 67, -2, 0, 33, 77};
	int i;
	int max=6;
	for(i=0; i<=max; i++)
		printf("%d,", dane[i]);
	for(i=max; i>=0; i--)
		printf("%d,", dane[i]);
	getchar();
	return 0;
}
```
**Zad. 2.** Napisz program, który podany tekst wyświetli wielkimi literami.
```c
#include <stdio.h>
#include <ctype.h>
#include <string.h>
int main(){
	int i;   
	char napis[]="ania";
	for (i=0; i<strlen(napis); i++)
	{
		napis[i]=toupper(napis[i]);
	}
	printf (napis);
	getchar ();
	return 0;
}
```
**Zad. 3.** Napisz funkcje sprawdzajaca, czy podana przez użytkownika liczba znajduje sie w powyższej tablicy.
```c
#include <stdio.h>
#include <string.h>
int main (){
	int i;
	int x;
	int y=0;
	int TABLICA [100]={2,4,6,8,10,12,14,16,18};
	printf ("\nWprowadz liczbe: ");
	scanf ("%d", &x);
	for (i=0; i<sizeof (TABLICA)/sizeof (TABLICA [0]); i++)
	{
		if (TABLICA [i]==x)
			y++;
	}
	if (y>0)
	{
		printf("\nPODANA LICZBA ZNAJDUJE SIE W TABLICY :)");
	}
	else
		printf("\nPODANA LICZBA NIE ZNAJDUJE SIE W TABLICY :(");
	getchar ();
	getchar ();
	return 0;
	for (i=0; i<100; i++)
	{
		printf ("%d", TABLICA [i]);
	}
	getchar ();
	return 0;
}
```
**Zad. 4.** Znajdź maksymalna liczbe w tablicy liczb zmiennoprzecinkowych podanych przez użytkownika.
```c
#include <stdio.h>
#define rozmiar 5               
double emax (double dane[]);    
int main () {
	double dane[rozmiar];
	double x;
	double max;
	int i;
	for (i = 0; i < rozmiar; i++) 
	{
		printf ("\nWprowadz liczbe nr %d: ", i + 1);
		scanf ("%lf", &x);
		dane[i] = x;
	}
	max = emax (dane);            
	for (i = 0; i < rozmiar; i++) 
		printf ("\nElemnt %d tablicy ma wartosc: %lf\n", i, dane[i]);
	printf ("\nElemnt najwiekszy z tablicy to: %lf", max);     
	getchar ();
	getchar ();
	return 0;
}
double emax (double dane[])            
{
	int i;
	double max = dane[0];        
	for (i = 0; i < rozmiar; i++)
	{
		if (dane[i] >= max)
			max = dane[i];
	}
	return max;
}
```
**Zad. 5.** Napisz funkcje obliczajaca srednia arytmetyczna z liczb zawartych w tablicy liczb zmiennoprzecinkowych.
```c
#include <stdio.h>
#define rozmiar 5
double esrednia (double dane[], int n);        
int main () {
	double dane[rozmiar];
	double x;
	double srednia;
	int i;
	for (i = 0; i < rozmiar; i++)
	{
		printf ("\nWprowadz liczbe nr %d: ", i + 1);
		scanf ("%lf", &x);
		dane[i] = x;
	}
	srednia = esrednia (dane, rozmiar);
	for (i = 0; i < rozmiar; i++)
		printf ("\nElemnt %d tablicy ma wartosc: %lf\n", i, dane[i]);
	printf ("\nSrednia to: %lf", srednia);
	getchar ();
	getchar ();
	return 0;
}
double esrednia (double dane[], int n)
{
	int i;
	double x;
	double suma = 0.0;
	for (i = 0; i < n; i++)
		suma += dane[i];
	return suma / rozmiar;
}
```
**Zad. 6.** Wypisz napis: char tekst [] = "Tablice to podstawa programowania." od końca do poczatku.
```c
#include <stdio.h>
int main () {
	char tekst[] = "Tablica to podstawa programowania.";
	int rozmiar = sizeof (tekst) / sizeof (char), i, j = rozmiar - 1;
	char rewers[rozmiar];
	for (i = 0; i < rozmiar; i++, j--)
		rewers[i] = tekst[j];
	for (i = 0; i < rozmiar; i++)
		printf ("%c", rewers[i]);
	getchar ();
	return 0;
}
```
**Zad. 7.** Napisz funkcje void odKonca (char napis []) która odwraca podany napis (taka funkcja jest potrzebna np. do zamiany liczby na system dwójkowy).
```c
#include <stdio.h>
#include <string.h>
#define rozmiar 32
void odKonca (char napis[]);
int main () {
	char napis[rozmiar];
	char c;
	int i;
	for (i = 0; i < rozmiar; i++) 
		napis[i] = '\0';
	i = 0;
	printf ("\nWprowadz napis: ");   
	while ((c = getchar ()) != '\n')
	{
		napis[i] = c;
		i++;
	}
	napis[i]='\0';                  
	printf ("\n%s\n\n", napis);       
	odKonca (napis);              
	printf (napis);                  
	getchar ();
	return 0;
}
void odKonca (char napis[])          
{
	int i;
	int j = strlen(napis) - 1;
	char rewers[strlen(napis)];
	for (i = 0; i < strlen(napis); i++, j--)
		rewers[i] = napis[j];
	for (i = 0; i < strlen(napis); i++)
		napis[i] = rewers[i];
}
```
**Zad. 8.** Napisz funkcje zwracajaca najmniejszy i najwiekszy element z tablicy liczb zmiennoprzecinkowych podanej jako argument funkcji.
```c
#include <stdio.h>
#define rozmiar 5
struct minMax {
	double min;
	double max;
};
struct minMax extr (double dane[], int n);    
int main () {
	double dane[rozmiar];
	double x;
	double min;
	double max;
	int i;
	struct minMax mM;
	for (i = 0; i < rozmiar; i++)
	{
		printf ("\nWprowadz liczbe nr %d: ", i + 1);
		scanf ("%lf", &x);
		dane[i] = x;
	}
	for (i = 0; i < rozmiar; i++)
		printf ("\nElemnt %d tablicy ma wartosc: %lf\n", i, dane[i]);
	mM = extr (dane, rozmiar);
	printf ("\nElement najmniejszy to: %lf\n\nElement najwiekszy to: %lf",mM.min, mM.max);
	getchar ();
	getchar ();
	return 0;
}
struct minMax extr (double dane[], int n)
{
	int i;
	double x;
	double min;
	double max;
	struct minMax mM;
	min = max = dane[0];
	for (i = 1; i < n; i++)
	{
		x = dane[i];
		if (x <= min)
			min = x;
		if (x >= max)
			max = x;
	}
	mM.min = min;
	mM.max = max;
	return mM;
}
```
**Zad. 9.** Napisać program, który pobiera od użytkownika n liczb i wczytuje je do tablicy. Napisać funkcje, która zwróci ostatnia liczbe tej tablicy podzielna przez 7.
```c
#include <stdio.h>
#define rozmiar 5
int jest7 (int dane[]);
int main () {
	int dane[rozmiar];
	int i;
	int x;
	int a;
	for (i = 0; i < rozmiar; i++)
	{
		printf ("\nWprowadz liczbe nr %d: ", i + 1);
		scanf ("%d", &x);
		dane[i] = x;
	}
	for (i = 0; i < rozmiar; i++)
		printf ("\nElemnt %d tablicy ma wartosc: %d\n", i, dane[i]);
	a = jest7 (dane);
	if (a == 1)
		printf ("\n\nNie wystepuje liczba podzielna przez 7");
	else
		printf ("\nOstatnia podana liczba podzielna przez 7 to: %d", a);
	getchar ();
	getchar ();
	return 0;
}
int jest7 (int dane[])
{
	int i;
	int x;
	int a = 1;
	for (i = 0; i < rozmiar; i++)
		if (dane[i] % 7 == 0)
			a = dane[i];
	return a;
}
```
**Zad. 10.** Napisz funkcje obliczajaca iloczyn skalarny dwóch wektorów n-wymiarowych.
```c
#include <stdio.h>
#define N 10                     
double iloczyn (double dane1[], double dane2[], int n);
void wysWekt(double dane[], int n);
void wprWekt(double dane[], int n);
int main () {
	double dane1[N];
	double dane2[N];
	double x;
	int i;
	int n;
	printf ("\nWprowadz rozmiar wektorow: ");
	scanf ("%d", &n);
	printf ("\nWprowadz skladowe pierwszego wektora:\n");
	wprWekt(dane1, n);
	puts (" ");  
	printf ("Wprowadz skladowe drugiego wektora:\n");
	wprWekt(dane2, n);
	printf ("\nWektor pierwszy = ");
	wysWekt(dane1, n);
	printf ("\n\nWektor drugi = ");
	wysWekt(dane2, n);
	x = iloczyn (dane1, dane2, n);   
	printf ("\n\nIloczyn skalarny tych wektorow wynosi = %lf.", x);
	getchar ();
	getchar ();
	return 0;
}
double iloczyn (double dane1[], double dane2[], int n)        
{
	int i;
	double x = 0.0;
	for (i = 0; i < n; i++)
		x += (dane1[i]) * (dane2[i]);
	return x;
}
void wysWekt(double dane[], int n)
{
	int i;
	printf ("[");
	for (i = 0; i < n; i++)
	{
		printf ("%lf", dane[i]);
		if (i < n - 1)
			printf (",");
	}
	printf ("].");
}
void wprWekt(double dane[], int n)
{
	int i;
	double x;
	for (i = 0; i < n; i++)       
	{
		printf ("\nnr %d: ", i + 1);
		scanf ("%lf", &x);
		dane[i] = x;
	}
}
```
**Zad. 11.** Napisz funkcje, która transponuje tablice kwadratowa double tab [128] [128] podana jako argument. Napisz i wykorzystaj funkcje void wyswietlMacierz (double m [128] [128], int wierszy, int kolumn);
```c
#include <stdio.h>
#define N 128                     
double trans (double tab[N][N], int wierszy, int kolumn);
void wyswietlMacierz (double m[N][N], int wierszy, int kolumn);
int main () {
	double tab[N][N];
	double tabT[N][N];
	double x;
	int i;
	int j;
	int wierszy;
	int kolumn;
	printf ("\nWprowadz ilosc wierszy: ");
	scanf ("%d", &wierszy);
	printf ("\nWprowadz ilosc kolumn: ");
	scanf ("%d", &kolumn);          
	for (i = 0; i < wierszy; i++)       
	{
		for (j = 0; j < kolumn; j++)   
		{
			printf ("\nWprowadz skladowa tablicy [%d,%d]: ", i + 1, j + 1);
			scanf ("%lf", &x);
			tab[i][j] = x;
		}
	}
	printf ("\n");         
	wyswietlMacierz (tab, wierszy, kolumn);
	printf ("\n");             
	for (i = 0; i < wierszy; i++)       
		for (j = 0; j < kolumn; j++)
			tabT[i][j] = tab[i][j];
	trans (tabT, wierszy, kolumn);
	wyswietlMacierz (tabT, kolumn, wierszy); 
	getchar ();
	getchar ();
	return 0;
}
double trans (double tab[N][N], int wierszy, int kolumn)
{
	double tabT[N][N];
	int i;
	int j;
	int k;
	for (i = 0; i < wierszy; i++)       
		for (j = 0; j < kolumn; j++)
			tabT[j][i] = tab[i][j];
	for (i = 0; i < kolumn; i++)      
		for (j = 0; j < wierszy; j++)
			tab[i][j] = tabT[i][j];
}
void wyswietlMacierz (double m[N][N], int wierszy, int kolumn)
{
	int i;
	int j;
	for (i = 0; i < wierszy; i++)
		for (j = 0; j < kolumn; j++)
			printf ("%lf %c", m[i][j], j == kolumn - 1 ? '\n' : ' ');
}
```
