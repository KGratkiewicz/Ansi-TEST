# Instrukcje warunkowe i operatory logiczne.
## Instrukcja warunkowa
Instrukcja warunkowa jest elementem języka programowania, który pozwala wykonać różne instrukcje zależnie od warunku podanego wewnątrz funkcji.

*Schemat (3.0) Instrukcja warunkowa*

![schemat 3 0 dv](https://user-images.githubusercontent.com/71324202/137342944-262366dd-0d01-4f00-a22b-a11ca58f84a7.png)

W języku C instrukcja warunkowa występuje w postaci instrukcji if (jeżeli) oraz else (w przeciwnym przypadku). Aby użyć funkcji warunkowej if w języku C należy postępować według następującego schematu.

```
if(warunek) { 
Kod do wykonania przy spełnieniu warunku
}

else { 
Kod do wykonania, jeżeli warunek się nie spełni
}
```

Gdzie w miejscu podpisany jako *warunek* należy podać wyrażenie logiczne lub zmienną, na której podstawie ma podjąć decyzję. Po instrukcji warunkowej pomiędzy klamrami należy wpisać kod, który chcemy wykonać w przypadku, gdy wynik działania wyrażenia podanego jako warunek będzie różne od 0. Do tworzenia warunków, w języku C używa się najczęściej operatorów relacji i logicznych. 

## Operatory relacji i operatory logiczne
W języku C występują operatory relacji, które zostały zawarte zostały w poniższej tabeli wraz z opisem:


### Operatory relacji
|Oznaczenie|Działanie|Przykład instrukcji z warunkiem|
| :-: | :----- | :------ |
|`==`|Równe|```if(a==b) /* jeżeli a równe b */ ```|
|`!=`|Różne|```if(a!=b) /* jeżeli a różne od b */ ```|
|`<`|Mniejsze|```if(a<b) /* jeżeli a mniejsze od b */  ```|
|`>`|Większe|```if(a>b) /* jeżeli a większe od b */  ```|
|`<=`|Mniejsze lub równe|```if(a<=b) /* jeżeli a mniejsze lub równe b */ ```|
|`>=`|Większe lub równe |```if(a>=b) /* jeżeli a większe lub równe b */ ```|


### Operatory logiczne
|Oznaczenie|Działanie|Przykład instrukcji z warunkiem|
| :-: | :----- | :------ |
|`&&`|Koniunkcja (AND)|```if(a==b && b<10) /* jeżeli a równe b i b mniejsze od 2 */ ```|
|`\|\|`|Alternatywa (OR)|```if(a>b \|\| a<0) /* jeżeli a większe od b lub a mniejsze od 0 */``` |
|`!`|Negacja (NOT)|```if(!(a<b)) /* jeżeli nie jest a mniejsze od b */ ```|

Wynikiem każdej z operacji logicznych jest wartość, która jest różna od zera w przypadku gdy warunek zostanie spełniony, lub równa zero kiedy przypadek nie zostanie spełniony. 

*Przykład (3.0) Wykorzystanie instrukcji warunkowej*

```
#include <stdio.h>
#include <stdlib.h>

int main() {
	int a,b;
	printf("Podaj dwie liczby: " );
	scanf(" %d %d",&a,&b);
	if(a==b)
		printf("Liczby sa rowne!");
	else 
		printf("Liczby sa rozne!");
	
	return 0;
}
```

*Wynik działania programu, dla dwóch zmiennych różnych:*

> Podaj dwie liczby: 3 2
>
> Liczby sa rozne!

*Wynik działania programu, dla dwóch zmiennych równych:*

> Podaj dwie liczby: 3 3
>
> Liczby sa rowne!

## Operator trójargumentowy ‘?’
W sytuacji gdzie normalnie musielibyśmy użyć instrukcji warunkowej, której efekt różni się jedynie jedną linią kodu można użyć operatora trójargumentowego ‘?’. Spójrzmy jak mógłby wyglądać kod z przykładu (3.0), gdyby użyć tam operatora ‘?’. 

*Przykład (3.1) użycie operatora ? zamiast prostej instrukcji warunkowej*
```
#include <stdio.h>
#include <stdlib.h>

int main() {
	int a,b;
	printf("Podaj dwie liczby: " );
	scanf(" %d %d",&a,&b);
	(a==b) ? printf("Liczby sa rowne!"):printf("Liczby sa rozne!");
	return 0;
}
```

*Wynik działania programu:*

> Podaj dwie liczby: 3 2
>
> Liczby sa rozne!

*lub:*

> Podaj dwie liczby: 3 3
>
> Liczby sa rowne!


Wyrażenie trójargumentowe składa się z 3 wyrażeń, pierwsze wyrażenie to wyrażenie logiczne, które warunkuje nam do której opcji zostaniemy przeniesieni. Następnie należy podać operator ‘?’ i kolejne dwa wyrażenia, oddzielone dwukropkiem. Pierwsze z nich wykona się w przypadku gdy wyrażenie 1 będzie prawdziwe, a drugie wykona się kiedy będzie fałszywe.

![operator trojargumentowy](https://user-images.githubusercontent.com/71324202/137337596-ca472807-799f-4232-b0dd-8a384cf82130.png)


*Przykład (3.2) wykonanie funkcji max(a,b) przy pomocy operatora ‘?’*

```
#include <stdio.h>
#include <stdlib.h>

int main() {
	int a,b;
	printf("Podaj dwie liczby: " );
	scanf(" %d %d",&a,&b);
	int c = (a==b) ? a : b ;
	return 0;
}
``` 


## Zadania do samodzielnego wykonania:
1. Stwórz program, który wczytuje od użytkownika 2 liczy całkowite i wyświetla:
   1. większą
   1. mniejszą
   1. relację jaka występuje pomiędzy pierwszą a drugą (np. 3<4, 5=5, 5>1)
1. Kalkulator, w którym użytkownik podaje 2 liczby, następnie podaje znak działania jakie chce wykonać (+, -, \*, /, %). Program wykonuje działanie i wyświetla wynik.
1. Napisz program, który pobiera 2 liczby od użytkownika a następnie stwierdza czy pierwsza jest podzielna przez drugą.
1. Napisz program, który oblicza średnią dla 5 ocen, oraz wyświetla, ile było ocen niedostatecznych.


