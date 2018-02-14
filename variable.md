## Les variables 

En Java, nous avons deux types de variables :

* Variables de type simple ou « primitif » ;
* Variables de type complexe ou des « objets ».

### Variables de type numérique
* **byte** (1 octet) : contient les entiers entre **-128 et +127**
* **short** (2 octets) : entre  **-32768 et +32767**
* **int** (4 octets) : de `-2*109 à 2*109` (2 et 9 zéros derrière. 
* **long** (8 octets): de `−9×1018−9×1018`  à `9×10189×1018` 
``` java
long anneeLumiere;
anneeLumiere = 9460700000000000L;
```
> ajouter `L` à la fin d'un nombre de type `long` pour infdiquer à lam machine virtuel qu'il s'agit bien d'un nombre `long`

* **float** (4 octets) : pour les nombres avec une virgule flottante

``` java
float nombre;
nombre = 2.0f;
```
> s'agissant d'un type `float` on écrit `.0` même s'il n'y à pas de chiffre après la virgule

> le `f` spécifit qu'il s'agit du'ne variable de type float

* **double** (8 octets) : identique au `float`mais avec plus de chiffre après la virgule **ET** pas de suffixe

``` java
double nombre;
nombre = 2.333333333333333333333d;
```
> le `d` spécifit qu'il s'agit du'ne variable de type double


Il est possible de séparer les variable de type numérique avec des underscores. 
> ATTENTION : placer les `_` uniquement entre deux chiffres  
``` java
double nombre = 1000000000000d;
//Peut s'écrire ainsi
double nombre = 1____000____000___000_000d; 
```


### Variables stockants des caractères

* **char** : contient un caractère stocké entre apostrophes (« ' ' »)

### Variables de type booléen

* **`true` OU `false`**

### Variables de type String

* Les variables de type `String` sont des variables complexes. 
* Les variables de type `String` sont appelés **`objet`**

```java
//Première méthode de déclaration
String phrase;
phrase = "Titi et Grosminet";

//Deuxième méthode de déclaration
String str = new String();
str = "Une autre chaîne de caractères";

//Troisième méthode de déclaration
String string = "Une autre chaîne";

//Quatrième méthode de déclaration
String chaine = new String("Et une de plus !");
```
**`String` n'est pas une variable mais un `objet`.** 

**La variable déclaré est donc un `objet`** == **On parle aussi `d'instance`**

> ex: 
la variable `chaine` ci dessus est une instance de la class `String` 

Les variables de type `String` sont des objets. 

Les objets sont définis par une ossature (un squelette) qui est en fait une classe. 

Ici, nous utilisons un objet `String` défini par une classe qui s'appelle « String » ; c'est pourquoi `String` a une majuscule et pas `int`,`float`, etc., qui eux ne sont pas définis par une classe.