
## Conversion ou Cast de variables
= conversion d'ajustement 

'Caster' une variable signifie changer son type.

**Ex 1** : forcer une variable à être de type `int`
``` java
int i = 123.452; 
// cette var ne peut pas être de type 'int', // elle devrait être de type `float`

// on peut tout de même la forcer à ếtre de type 'int' grace au "casting"

int i = (int) 123.452; // retourne 123 
```
> Cela permet d'obliger un nombre à virgule (norrmalement de type `float`) à ce comporter comme une variable de type `int` (nombre entier sans virgule)

**Ex 2** : conversion d'un type `int` en type `float`:
``` java
int i = 123;
float j = (float)i;
// retourne 123.0
```

**Ex 3** : Caster des oppérations complètes
``` java
int nbre1 = 3, nbre2 = 2;
double resultat = nbre1 / nbre2;

System.out.println("Le résultat est = " + resultat);
``` 

**Ex 4** : passer d'un type `int` à un type `string`
``` java
/****************
int --> String
*****************/
int i = 12;
String j = new String();
j = j.valueOf(i);


/****************
String --> int
*****************/
int i = 12;
String j = new String();
j = j.valueOf(i);
int k = Integer.valueOf(j).intValue();
``` 
### Le Cast présente des rique de pertes de précisions 

**Cas 1** 

```java
int i = 123.452;
int i = (int) 123.452; // retourne 123
```
> on perd les chiffre après la virgule. affichera 123 peut importe la valeur des chiffres après la virgule 

**Cas 2**

``` java
/****************** 
    EXEMPLE 1 
*******************/

int nbre1 = 3, nbre2 = 2;
double resultat = nbre1 / nbre2;
System.out.println("Le résultat est = " + resultat) // Retourne 1 

/*****************
    EXEMPLE 2 
******************/

int nbre1 = 3, nbre2 = 2;
double resultat = (double)(nbre1 / nbre2);
System.out.println("Le résultat est = " + resultat); // Retourne egallement 1 
```
> En java il existe des **priorités d'oppérations**
> Ici le code s'éxecute comme suis : 
> 1. fait le calcul (ici de deux `int` --> 3/2),
>> retourne 1 et pas 1.5 (car il sagit de 2 `int`) 
> 2. caste le résultat en `double`
>> convertie 1 en variable de type `double`
> 3. affecte le resultat de l'oppération dans notre variable `resultat`.
>> `résultat` vaut donc 1 et non 1.5 en raison de la priorité d'oppérations

Pour avoir un résultat correct, il faudrait caster chaque nombre avant de faire l'opération, comme ceci :
``` java
int nbre1 = 3, nbre2 = 2;
double resultat = (double)(nbre1) / (double)(nbre2); // résultat = 1.5
```

**Exemple de priorité des oppérateurs : `<` ET `++`
``` java
/*****************
    < avant ++ 
******************/

// ici a est comparé à b pui a est incrémenté
int a = 1, b = 15;
while (a++ < b)
   System.out.println("coucou " +a+ " fois !!");

/*****************
    ++ avant < 
******************/

// ici a est incrémenté puis comparé à b
int a = 1, b = 15;
while (++a < b)
  System.out.println("coucou " +a+ " fois !!");
```