# TUTO JAVA 

test 

[page 2](https://gregstone.github.io/page2)

## Divers tuto 

[OpenClassRooms](https://openclassrooms.com/courses/apprenez-a-programmer-en-java/installer-les-outils-de-developpement)

pgkgpfpĝkpdkgfdkgpfdg
## A revoir 
* this 
* Encapsulation
* super()
* protected

## Plugins avec Eclipse

Les plugins se présente souvent comme un dossier contenant généralement deux sous-dossiers : 
* un dossier « plugins »
* un dossier « features ». 


Ces dossiers existent aussi dans le répertoire d'Eclipse. Il vous faut donc copier le contenu des dossiers de votre plugin vers le dossier correspondant dans Eclipse (pluginsdanspluginsetfeaturesdansfeatures).

## DEFINITION 

* **JRE : Java Runtime Environment** = Machine virtuel java. 

Lors de la compilation du code, celui-prend une forme intermédiaire --> **byte code**

* **JDK: Java Development Kit** 

Contient l'ensemble des fonctionnalités du JRE + éléments nécessaire pour le développement, la compilation...

**SI** on utilise un IDE, celui ci contient déjà tout le nécessaire pour le développement **ALORS** le JRE etst donc suffisant 

* J2SE : Standard edition : application "clients lourds" (word, excel..)
* J2EE: Entreprise Edition: application web 
* J2ME : Micro Edition : appli pour mobiles 


* **Class** : 

Une classe est un ensemble de codes contenant plusieurs instructions que doit effectuer votre programme. Ne vous attardez pas trop sur ce terme, nous aurons l'occasion d'y revenir.

* **Byte code** : code intermédiaire entre votre code Java et le code machine

Le **byte code** se trouve dans les fichiers précompilés de vos programmes

Fichier source a pour extension `.java` et un fichier précompilé a l'extension `.class`


**Un programme JAVA c'est au minimum :**
* une `CLASS` contenant une **méthode** `main`

* **Méthode** : une méthode est une suite d'instruction à executer 

## Premier programmes

* **Exemple basique 

``` java
public class testclass {
    public static void main(String[] args){
        System.out.print("Hello World !");
    }
}
```
> Class `testclass` : `plublic class test class {}`


> Méthode `main` : 
``` java
public static void main(String[] args){ }
```
>> `void` signifie : ne retourne rien 

> Code à executer : 
``` java
System.out.print("Hello World !");
```
> Class `System`    <br>
> objet `out`       <br>
> méthode `print`   <br>

`println()` : Variante incluant des saut de lignes 

`/n` : variante pour les aut de lignes

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

## Lecture des entrée claviers 

Les variables `String` sont enréalité des objets de type `Sting`. Ainsi pour que JAVA puisse lire ce que l'on tape au clavier on doit utiliser un objet de type `Scanner`
 
**= La lecture des entrées clavier se fait via l'objet `Scanner`.**
* Ce dernier se trouve dans le package java.util à importer. `import java.util.Scanner;`

Pour pouvoir récupérer ce vous allez taper dans la console, vous devrez initialiser l'objet `Scanner` avec l'entrée standard, `System.in`.

``` java
Scanner sc = new Scanner(System.in);
```

Il y a une méthode de récupération de données pour chaque type (sauf les `char`) : `nextLine()` pour les `String`, `nextInt()` pour les `int` ...

``` java
/*
#####################################
RECUPERATION DE LA SAISIE AU CLAVIER
#####################################
*/
Scanner sc = new Scanner(System.in);
System.out.println("Veuillez saisir un mot :");
String str = sc.nextLine();
System.out.println("Vous avez saisi : " + str);

/*
########################################
RECUPERATION DE LA SAISIE DE TYPE `CHAR`
########################################
*/
System.out.println("Saisissez une lettre :");
Scanner sc = new Scanner(System.in);

// On récupère une chaine de caractère
String str = sc.nextLine();

// On utilise la méthode 'charAt()' de l'objet 'String' pour récupérer le premier caratère
char carac = str.charAt(0);
System.out.println("Vous avez saisi le caractère : " + carac);
```

ATTENTION : la méthode `nextline()` récupère le contenu de toute la ligne et replace la tête de lecture au début d'une autre ligne 
```java

/*
###################################################
                    PROBLEME
###################################################
*/
import java.util.Scanner;

public class Main {
  public static void main(String[] args){
    Scanner sc = new Scanner(System.in);
    System.out.println("Saisissez un entier : ");
    int i = sc.nextInt();
    System.out.println("Saisissez une chaîne : ");
    String str = sc.nextLine();      
    System.out.println("FIN ! ");
   }
}

// … ne vous demandera pas de saisir une chaîne et affichera directement « Fin ». Pour pallier ce problème, il suffit de vider la ligne après les instructions ne le faisant pas automatiquement :

/*
###################################################
                    SOLUTION 
###################################################
*/
import java.util.Scanner;

public class Main {
  public static void main(String[] args){
    Scanner sc = new Scanner(System.in);
    System.out.println("Saisissez un entier : ");
    int i = sc.nextInt();
    System.out.println("Saisissez une chaîne : ");
    //On vide la ligne avant d'en lire une autre
    sc.nextLine();
    String str = sc.nextLine();      
    System.out.println("FIN ! ");
  }
}
``` 
## lES CONDITIONS 

### Le switch 

``` java 
/*
###################################################
                    SYNTAX 
###################################################
*/
switch (/*Variable*/)
{
  case /*Argument*/:
    /*Action*/;
    break;        
  default:
    /*Action*/;             
}
```
> 1. La classe évalue l'expression figurant après le switch (ici /*Variable*/).
> 2. **SI** la première languette (`case /*Valeur possible de la variable`) correspond à la valeur de `/*Variable*/`, l'instruction figurant dans celle-ci sera exécutée.
> 3. **SINON**, on passe à la languette suivante, et ainsi de suite.
> 4. Si aucun des cas ne correspond, la classe va exécuter ce qui se trouve dans l'instruction default:/*Action*/;
> `break` permet de sortir du switch si une condituition correspond (mettre un `break` après chaque `case`)

## Les tableaux 

### Tableau à une dimmension
* Il existe autant de tableau que de type de variable 
* Chaque tableau à un type donné et ne peut donc accepter que les variables de ce type

``` java
/*
###################################################
                    SYNTAX 
###################################################
*/
<type du tableau> <nom du tableau> [] = { <contenu du tableau>};

/*
###################################################
                    EXEMPLE 
###################################################
*/
int tableauEntier[] = {0,1,2,3,4,5,6,7,8,9};
double tableauDouble[] = {0.0,1.0,2.0,3.0,4.0,5.0,6.0,7.0,8.0,9.0};
char tableauCaractere[] = {'a','b','c','d','e','f','g'};
String tableauChaine[] = {"chaine1", "chaine2", "chaine3" , "chaine4"};

/*
###################################################
            DECLARATION TABLEAU VIDE 
###################################################
*/
int tableauEntier[] = new int[6];
//Ou encore
int[] tableauEntier2 = new int[6];
// ici on initialise un tableau vide avec 6 cases
```
> **Tableau vide :** il faut impérativement indiquer le nombre d'éléments que contiendra le tableau

### Tableau multi dimentionnelle

**DEFINITION** : Tableau contenant au minimum 2 tableau

``` java
int premiersNombres[][] = { {0,2,4,6,8},{1,3,5,7,9} };
// tableau avec 2 lignes : 1 ligne avec {0,2,4,6,8}, une 2ème ligne avec {1,3,5,7,9}  
```
* `premiersNombres[0][0]` correspondra au premier élément de la ligne paire
* `premiersNombres[1][0]` correspondra au premier élément de la ligne impaire.

## Les Méthodes de Class 
Méthode = fonction 

* **Les méthodes ne sont pas limités en nombre de paramètres**
* **Il existe 3 types de méthodes :**
  * méthode qui ne renvoient rien = méthode de type `void`
  * méthode qui renvoient des types primitifs = méthode de type `double` `int` `char`.....
  * méthode qui retournent des objets = `String`.... 


### **Exemple de méthode de class 

* `toLowerCase()`
* `equals()`= vérifier si deux chaines de caractères sont identiques 
``` java 
String str1 = new String("coucou"), str2 = new String("toutou");
if (str1.equals(str2)) 


// vérifier su 2 chaines ne sont pas identiques
String str1 = new String("coucou"), str2 = new String("toutou");

if (!str1.equals(str2))
  System.out.println("Les deux chaînes sont différentes !");
```

* `charAt()` : extraction de caractères. Ne peut être réalisé que sur des `String`
> comment à 0
* `substring()` : Extrait une partie d'une chaine de caractère. 
> Prend 2 arguments : la postion du premier caratère à inclure dans la chaine ET la position du premier caratère exclus de la chaine de caratère
``` java 
String chaine = new String("la paix niche"), chaine2 = new String();
chaine2 = chaine.substring(3,13);   //Permet d'extraire "paix niche" 
```
* `indexOf()`
``` java
String mot = new String("anticonstitutionnellement");
int n = 0;
n = mot.indexOf('t'); //n vaut 2
```

## La surcharge de méthode 

La surcharge de méthode consiste à garder le nom d'une méthode (donc un type de traitement à faire : pour nous, lister un tableau) et à changer la liste ou le type de ses paramètres.

Ex : nous voulons que notre méthode `parcourirTableau` puisse parcourir n'importe quel type de tableau. 
* Nous allons donc surcharger notre méthode afin qu'elle puisse aussi travailler avec des `int`,
``` java 
/* 
############################################
        SURCHARGER UNE METHODE 
############################################
*/
static void parcourirTableau(String[] tab)
{
  for(String str : tab)
    System.out.println(str);
}       

static void parcourirTableau(int[] tab)
{
  for(int str : tab)
    System.out.println(str);
}
```
> On à surcharger la méthode `parcourirTableau` : celle ci peut désormais parcourir : 1. des tableaux d'entiers , 2. des tableau de string

Pour Java, le fait de surcharger une méthode lui indique qu'il s'agit de deux, trois ou X méthodes différentes, car les paramètres d'appel sont différents. Par conséquent, Java ne se trompe jamais d'appel de méthode, puisqu'il se base sur les paramètres passés à cette dernière.

### Méthode `final`

Méthode figée: impossible de la redéfinir (ex: méthode `getClass()`) 

``` java
public final int maMethode(){
  //Méthode ne pouvant pas être surchargée
}
```

## LES CLASSE : Première classe 

**Instance de classe** : 
  * `String str = new String("tiens… un objet String");`
  * `str` est un objet `String`
  * ici on à utilisé un objet de la classe `String`
  * on à crée une instance (= un objet) de la classe `String()`
    * créer un objet ayant un comportement et un état définis par la classe  
    * l'objet constitu un exemplaire de la classe

### Structures de bases 

Classe = moule 
Lorsqu'on remplis ce moule (= la classe), cela donne **UN OBJET** ayant la forme du moule et ses caractérisitques  

#### Portée
* **public** : Tout le monde peut appeler l'élément déclaré en 'public' 
* **private** : une méthode 'private' ne peut être appelé que depuis l'intérieur de la classe dans laquelle elle ce trouve

#### **Exemple : Création d'un objet Ville

1. DECLARER LA CLASSE Ville 


```java 
/*******************************
DECLARATION DE LA CLASSE VILLE
********************************/

public class Ville {

}
``` 
> **Nom des classe = commence par une majuscule**

2. DETERMINER LES DONNÉES À ATTRIBUER A NOTRE OBJET Ville

**Une ville possède :**  
* un nom, sous la forme d'une chaîne de caractères ;
* un nombre d'habitants, sous la forme d'un entier ;
* un pays apparenté, sous la forme d'une chaîne de caractères.

> Afin d'attribuer les données à notre objet Ville on utilise des varaible d'instances 
``` java
public class Ville{
  String nomVille; // variable nomVille qui est une instance de la classe String
  String nomPays;
  int nbreHabitants; 
}
```
-----
**TYPES DE VARIABLES**
* Variables d'instances (public par défaut quand déclaré à l'intérieur du'ne classe) : définiront les caractéristiques de notre objet.
* Variables de classe : celles-ci sont communes à toutes les instances de votre classe.
* Variables locales : ce sont des variables que nous utiliserons pour travailler dans notre objet

------
##### CREER UN OBJET 

3. CREER UN CONSTRUCTEUR "PAR DEFAUT"

**Constructeur :** méthode d'instance (fonction d'un objet) qui va se charger de:
* créer un objet
* initialiser ses variables de classes

La méthode `constructeur` à pour fonction d'indiquer à la JVM qu'il faut réserver de l'espace pour notre futur objet 

Le premier contructeur est généralement appelé `constructeur oar defaut`, celui-ci : 
* ne prend pas de paramètres 
* **permet tout de même d'instancier un objet**
* On initialise à l'intérieur nos variables d'instances 

``` java
//Constructeur par défaut
  public Ville(){

    System.out.println("Création d'une ville !");      
    nomVille = "Inconnu";
    nomPays = "Inconnu";
    nbreHabitants = 0;
  } 
```
> Le/les constructeurs portent le même nom que la classe 

<br>

-------

4. CREER UNE INSTANCE DE LA CLASSE `Ville`

> une instance d'objet se fait grace au mot clé `new`

``` java
public class TestClass{ 

  public static void main(String[] args){   
    Ville ville = new Ville(); // instnace de l'objet Ville
//    1     2         3 
  } 
}
```
1. `Ville` = type de l'objet à créer 
2. `ville` = nom de le l'objet 
3. `new Ville()` = instance de la classe Ville() = Création de l'objet

----

5. INSÉRER DES DONNÉS DANS NOTRE INSTANCE (= objet) DE LA CLASSE Ville

A ce stade on doit mettre des données dans notre objet afin de pouvoir commencer à travailler

**Exemple**
``` java 
/*
##########################################################
          CREATION D'OBJET AVEC DES DONNES
##########################################################
*/
Ville ville1 = new Ville("Marseille", 123456789, "France");
```
> On créer un objet (= instance de la classe Ville) contenant des données  
> les données sont passées en paramètre : `"Marseille", 123456789, "France"`

Pöur pouvoir passer des paramètres à notre objet on doit : 
* **Créer une méthode qui**  
  * récupére les paramètres passés ("Marseille"...)
  * initialise les variables de notre objet. 

  Cette méthode est appelé `constructeur d'initialisation`

``` java 
public class Ville {
 
  //Stocke le nom de notre ville
  private String nomVille;
  //Stocke le nom du pays de notre ville
  private String nomPays;
  //Stocke le nombre d'habitants de notre ville
  private int nbreHabitants;
 
  //Constructeur par défaut
  public Ville(){
    System.out.println("Création d'une ville !");          
    nomVille = "Inconnu";
    nomPays = "Inconnu";
    nbreHabitants = 0;
  }
 
  //Constructeur avec paramètres
  //J'ai ajouté un « p » en première lettre des paramètres.
  public Ville(String pNom, int pNbre, String pPays)
  {
    System.out.println("Création d'une ville avec des paramètres !");
    nomVille = pNom;
    nomPays = pPays;
    nbreHabitants = pNbre;
  }        
}
```
**ATTENTION** : Lors de la création il faut respecter l'ordre des paramètres passés lors de l'initialisation (ordre définit dans le constructeur) 

``` java
//L'ordre est respecté -> aucun souci
Ville ville1 = new Ville("Marseille", 123456789, "France");
//Erreur dans l'ordre des paramètres -> erreur de compilation au final
Ville ville2 = new Ville(12456, "France", "Lille");
```
> on doit impérativement déclarer les variables d'instance en private 

> Sinon le contenu de celle-ci sont pmodfifiable depuis la methode `main` de la manière suivante : 
``` java 
// accéder et modifier une variable d'instance
// A EVITER  
ville.nomVille = "la tête à toto ! ! ! !";
```
Une fois déclaré en `private`, les variables ne sont plus accessible depuis la méthode `main`
Pour y accéder tout de même on utilise un `accesseur` et un `mutateur`

### Accesseur et mutateur 

**Accesseur (= getters)**: méthode qui va nous permettre d'accéder aux variables de nos objets en lecture

**Mutateur (= setters)**: méthode qui permet d'accéder aux varaibles des object en écriture

Grâce aux accesseurs, vous pourrez afficher les variables de vos objets, et grâce aux mutateurs, vous pourrez les modifier

``` java
public class Ville {

  //Les variables et les constructeurs n'ont pas changé…
          
  /*
  ###########################################
            ACCESSEUR  (lecture)
  ###########################################
  */

  //Retourne le nom de la ville
  public String getNom()  {  
    return nomVille;
  }

  //Retourne le nom du pays
  public String getNomPays()
  {
    return nomPays;
  }

  // Retourne le nombre d'habitants
  public int getNombreHabitants()
  {
    return nbreHabitants;
  } 
 
  /*
  ###########################################
          MUTATEUR  (modification)
  ###########################################
  */

  //Définit le nom de la ville
  public void setNom(String pNom)
  {
    nomVille = pNom;
  }

  //Définit le nom du pays
  public void setNomPays(String pPays)
  {
    nomPays = pPays;
  }

  //Définit le nombre d'habitants
  public void setNombreHabitants(int nbre)
  {
    nbreHabitants = nbre;
  }  
}
```
> Accesseur = 
* `getNom()`
* méthode public (donc accessible depuis l'exterieur)
* de même type que la varaible qu'il retourne

> Mutateur = 
* `setNom()`
* de type `void` = ne retourne aucune valeur, les mutateur se contente de mettre à jour les varaibles


``` java
Ville v = new Ville();
Ville v1 = new Ville("Marseille", 123456, "France");       
Ville v2 = new Ville("Rio", 321654, "Brésil");

/*
####################################################
    CHANGER VALEUR DES VARIABLES (2 méthodes) 
####################################################
*/
/***************************************************
  1 - Avec un nouvel objet 
  
  Nous allons interchanger les Villes v1 et v2.        
****************************************************/       
Ville temp = new Ville();
temp = v1;
v1 = v2;
v2 = temp;
       
System.out.println(" v1 = "+v1.getNom()+" ville de  "+v1.getNombreHabitants()+ " habitants se situant en "+v1.getNomPays());
System.out.println(" v2 = "+v2.getNom()+" ville de  "+v2.getNombreHabitants()+ " habitants se situant en "+v2.getNomPays()+"\n\n");

/***************************************************
  2 - Avec le Mutateur 
  
  Nous allons interchanger les Villes v1 et v2.        
****************************************************/

v1.setNom("Hong Kong");
v2.setNom("Djibouti");
      
System.out.println(" v1 = "+v1.getNom()+" ville de  "+v1.getNombreHabitants()+ " habitants se situant en "+v1.getNomPays());
System.out.println(" v2 = "+v2.getNom()+" ville de  "+v2.getNombreHabitants()+ " habitants se situant en "+v2.getNomPays()+"\n\n"); 
```

------
Les différents types de méthodes dans un objet : 
* les constructeurs -> méthodes servant à créer des objets ;
* les accesseurs -> méthodes servant à accéder aux données des objets ;
* les méthodes d'instance → méthodes servant à la gestion des objets.
------

### Utilisation de `this` (A revoir)

**Accès aux méthodes d'un objet :**
* Accéder au méthode d'un objet depuis l'exterieur = `objet.variable` ---> `ville.nomVille`
* Accéder au méthode d'un objet depuis l'intérieur = `this`

Pour simplifier,`this` fait référence à l'objet courant ! 

Bien que la traduction anglaise exacte soit « ceci », il faut comprendre « moi ». À l'intérieur d'un objet, ce mot clé permet de désigner une de ses variables ou une de ses méthodes.

``` java
public class Ville {
 
  private String nomVille;
  private String nomPays;
  private int nbreHabitants;
  private char categorie; // créer une var catégorie
   
  public Ville(){
    System.out.println("Création d'une ville !");          
    nomVille = "Inconnu";
    nomPays = "Inconnu";
    nbreHabitants = 0;
    this.setCategorie();
  }
 
  public Ville(String pNom, int pNbre, String pPays)
  {
    System.out.println("Création d'une ville avec des paramètres !");
    nomVille = pNom;
    nomPays = pPays;
    nbreHabitants = pNbre;
    this.setCategorie();
  }  
    
  //Retourne le nom de la ville
  public String getNom()  {  
    return nomVille;
  }

  //Retourne le nom du pays
  public String getNomPays()
  {
    return nomPays;
  }

  // Retourne le nombre d'habitants
  public int getNombreHabitants()
  {
    return nbreHabitants;
  } 

  //Retourne la catégorie de la ville
  public char getCategorie()
  {
    return categorie;
  } 
 
  //Définit le nom de la ville
  public void setNom(String pNom)
  {
    nomVille = pNom;
  }

  //Définit le nom du pays
  public void setNomPays(String pPays)
  {
    nomPays = pPays;
  }

  //Définit le nombre d'habitants
  public void setNombreHabitants(int nbre)
  {
    nbreHabitants = nbre;
    this.setCategorie();
  }  
 
  //Définit la catégorie de la ville
  private void setCategorie() {
 
    int bornesSuperieures[] = {0, 1000, 10000, 100000, 500000, 1000000, 5000000, 10000000};
    char categories[] = {'?', 'A', 'B', 'C', 'D', 'E', 'F', 'G', 'H'};

    int i = 0;
    while (i < bornesSuperieures.length && this.nbreHabitants > bornesSuperieures[i])
      i++;

    this.categorie = categories[i];
  }

  //Retourne la description de la ville
  public String decrisToi(){
    return "\t"+this.nomVille+" est une ville de "+this.nomPays+ ", elle comporte : "+this.nbreHabitants+" habitant(s) => elle est donc de catégorie : "+this.categorie;
  }

  //Retourne une chaîne de caractères selon le résultat de la comparaison
  public String comparer(Ville v1){
    String str = new String();

    if (v1.getNombreHabitants() > this.nbreHabitants)
      str = v1.getNom()+" est une ville plus peuplée que "+this.nomVille;
     
    else
      str = this.nomVille+" est une ville plus peuplée que "+v1.getNom();
     
    return str;
  }
}
```
**La méthode `setCategorie()`**

Elle ne prend aucun paramètre, et ne renvoie rien : elle se contente de mettre la variable de classe `categorie` à jour. Elle détermine dans quelle tranche se trouve la ville grâce au nombre d'habitants de l'objet appelant, obtenu au moyen du mot clé `this`. Selon le nombre d'habitants, le caractère renvoyé changera. Nous l'appelons lorsque nous construisons un objet `Ville`(que ce soit avec ou sans paramètre), mais aussi lorsque nous redéfinissons le nombre d'habitants : de cette manière, la catégorie est automatiquement mise à jour, sans qu'on ait besoin de faire appel à la méthode.

**La méthode `decrisToi()`**

Celle-ci nous renvoie un objet de type `String`. Elle fait référence aux variables qui composent l'objet appelant la méthode, toujours grâce à `this`, et nous renvoie donc une chaîne de caractères qui nous décrit l'objet en énumérant ses composants.

**La méthode `comparer(Ville V1)`**

Elle prend une ville en paramètre, pour pouvoir comparer les variables `nbreHabitants` de l'objet appelant la méthode et de celui passé en paramètre pour nous dire quelle ville est la plus peuplée !

------

Dans cette méthode, nous voulons comparer le nombre d'habitants de chacun des deux objets `Ville` 

Pour accéder à la variable `nbreHabitants` de l'objet `V2`, il suffit d'utiliser la syntaxe `V2.getNombreHabitants();`
* nous ferons donc référence à la propriété `nbreHabitants` de l'objet `V2`. 

Mais l'objet `V`, lui, est l'objet appelant de cette méthode. Pour se servir de ses propres variables,on utilise alors `this.nbreHabitants`, 
* appel la variable `nbreHabitants` de l'objet exécutant la méthode `comparer(Ville V)`.


### Les variables de classes (A revoir)

Rappel : **Variables d'instances** = carte d'identité de notre objet

**VARIABLES DE CLASSES** : 
* doit contenir le mot clé `static`
Static : tous les objets partages les variables static. compilé avec l'objet directement (exige plus de memoire). On peut y accéder sans instancier l'objet
* celle ci sont communes à toutes les instances de la classe
* Les méthodes n'utilisant que des variables de classe doivent elles aussi être déclarées `static`

**Exemple : Créer une varaible de classes pour compter le nombre d'instances**
Cette varaibles aura les caractéristiques suivantes: 
* type : `int`
* nom : `nbreInstance`
* variable `public`

On créer egalement une coppie de cette même variable : 
* nom : `nbreInstanceBis`
* varaible `private`

``` java
public class Ville {
   
  //Variables publiques qui comptent les instances
  public static int nbreInstances = 0;

  //Variable privée qui comptera aussi les instances
  private static int nbreInstancesBis = 0;        
  
  //Les autres variables n'ont pas changé

  public Ville(){
    //On incrémente nos variables à chaque appel aux constructeurs
    nbreInstances++;
    nbreInstancesBis++;          
    //Le reste ne change pas.
  }

  public Ville(String pNom, int pNbre, String pPays)
  {  
    //On incrémente nos variables à chaque appel aux constructeurs
    nbreInstances++;
    nbreInstancesBis++;          
    //Le reste ne change pas
  }
  public static int getNombreInstancesBis() // méthode déclaré static car elle n'utilise que des varaibles de classes
  {
    return nbreInstancesBis;
  }  
  //Le reste du code est le même qu'avant
}
```
### L'encapsulation 

Voilà, vous venez de construire votre premier objet « maison ». Cependant, sans le savoir, vous avez fait plus que ça : vous avez créé un objet dont les variables sont protégées de l'extérieur. En effet, depuis l'extérieur de la classe, elles ne sont accessibles que via les accesseurs et mutateurs que nous avons défini. C'est le principe d'encapsulation !

En fait, lorsqu'on procède de la sorte, on s'assure que le fonctionnement interne à l'objet est intègre, car toute modification d'une donnée de l'objet est maîtrisée. Nous avons développé des méthodes qui s'assurent qu'on ne modifie pas n'importe comment les variables.

### L'heritage (protected, super())

Imaginons que, dans le programme réalisé précédemment, nous voulions créer un autre type d'objet : des objets `Capitale`. Ceux-ci ne seront rien d'autre que des objets `Ville` avec un paramètre en plus... disons un monument. 

Vous n'allez tout de même pas recoder tout le contenu de la classe `Ville` dans la nouvelle classe ! 

Déjà, ce serait vraiment contraignant, mais en plus, si vous aviez à modifier le fonctionnement de la catégorisation de nos objets `Ville`, vous auriez aussi à effectuer la modification dans la nouvelle classe… Ce n'est pas terrible.

**L'héritage permet à des objets de fonctionner de la même façon que d'autres.**

**Permet de** 
* Créer des classes héritées (= classes dérivées) de nos classes mères (aussi appelées classes classes de base).
* Nouys pouvons nous servir d'une classe dérivée comme une classe mère pour créer de nouvelles classes dérivées 
* Le mot clés `extends` permet de créer un héritage
* Les classes hérités peuvent accéder à toutes les ressources `public` ou `protected` de la classe mère

**`PROTECTED`** : les éléments `protected` sont accessibles uniquement par les classes filles.  

* une classe fille (= dérivée) ne peut hériter que d'une seul classe mère (pas d'héritage multiples possibles)

**Exemple** : créer une nouvelle classe `Capitale`, héritée de `Ville` 

Les objets `Capitale` auront tous les attributs et toutes les méthodes associés aux objets `Ville`!

``` java
/*##############################
  CREATION D'UNE CLASSE HERITÉ 
################################ */
class Capitale extends Ville {

}
// ON CRÉER UNE CLASSE CAPITAL HÉRITÉ DE LA CLASSE VILLE
```
#### Super()

**`super()`** : permet de faire appel au variables de la classe mère dans les constructeurs fille.**Récupère les éléments de l'objet mère et les envoi à l'objet fille**
``` java
class Capitale extends Ville {
 
  private String monument;
 
  //Constructeur par défaut
  public Capitale(){
    //Ce mot clé appelle le constructeur de la classe mère  
    super();
    monument = "aucun";
  }
}
```
> `super()` appel le contructeur par défaut de la classe mère `Ville` dans la classe fille `Capitale`

* `super()` fonctionne egalement pour les méthodes de classes

> Pour que la méthode mère `decrisToi` prennene en compte le champs `monument` créer dans la classe fille on utilise egalement `super`

``` java
class Capitale extends Ville {
  private String monument;
 
  public Capitale(){
    //Ce mot clé appelle le constructeur de la classe mère  
    super();
    monument = "aucun";
  } 

  public String decrisToi(){
    String str =  super.decrisToi() + "\n \t ==>>" + this.monument+ " en est un monument";
    System.out.println("Invocation de super.decrisToi()");
    
    return str;
   }
}
```

``` java
/*
######################################
    CONSTRUCTEUR D'INITIALISATION
###################################### */

//Constructeur d'initialisation de capitale
  public Capitale(String nom, int hab, String pays, String monument){
    super(nom, hab, pays);
    this.monument = monument;
  }    
```

``` java
/* 
######################################
CLASSE HÉRITÉ 'Capitale' COMPLETE 
######################################
*/ 
public class Capitale extends Ville {
     
  private String monument;
    
  //Constructeur par défaut
  public Capitale(){
    //Ce mot clé appelle le constructeur de la classe mère
    super();
    monument = "aucun";
  }    
      
  //Constructeur d'initialisation de capitale
  public Capitale(String nom, int hab, String pays, String monument){
    super(nom, hab, pays);
    this.monument = monument;
  }    
     
  /**
    * Description d'une capitale
    * @return String retourne la description de l'objet
  */
  public String decrisToi(){
    String str = super.decrisToi() + "\n \t ==>>" + this.monument + "en est un monument";

    return str;
    } 

  /**
    * @return le nom du monument
  */
  public String getMonument() {
    return monument;
  } 

  //Définit le nom du monument
  public void setMonument(String monument) {
    this.monument = monument;
  }   
}
```

### POLYMORPHISME

**Permet de manipuler des objets sans connaitre leur type**

Dans notre exemple, vous avez vu qu'il suffisait d'utiliser la méthode `decrisToi()` sur un objet `Ville` ou sur un objet `Capitale`. On pourrait construire un tableau d'objets et appeler `decrisToi()`sans se soucier de son contenu : villes, capitales, ou les deux.

On appel une classe parente pour faire référence à un objet enfant 

----
Ressources : 
* [pooverloading / overiding / polymorphism ](https://www.youtube.com/watch?v=te1mmSSeHyE)
overloading = compilation   (à la compilation) 
overiding = runtime        (à l'execution)
* [polymorphism](https://www.youtube.com/watch?v=v_ZBH1RsJqU)
---- 

  #### 1. OVERIDING  = Polymorphisme à l'éxecution = polymorphisme dynamique 

**Exemple** : 
* on a une classe parente `Animal` et deux classes enfant `Horse` et `Cat`
* `Animal` possède une méthode `sound()` 

```java
public class Animal{
   ...
   public void sound(){
      System.out.println("Animal is making a sound");   
   }
}
```

> ici on veut renvoyer le bruit effectué par chaque animale

> La classe `Animal` étant généraliste, on ne peut pas différencié le bruit effectué par chaque animale. **Pour différencier le bruit de chaque animale on utilise le polymorphisme**

* La classe `Horse` extands la classe `Animal`
* La classe `Horse` récupère l'ensemble des méthodes de `Animal`
* La classe `Horse` possède egalement une méthode `sound()` pour laquel nous pouvons spécifier un bruit particulié

``` java
public class Horse extends Animal{
...
    @Override
    public void sound(){
        System.out.println("Neigh");
    }
}
```
* La classe `Cat` extands la classe `Animal`

``` java
public class Cat extends Animal{
...
    @Override
    public void sound(){
        System.out.println("Meow");
    }
}
```

  #### 2. OVERLOADING  = Polymorphisme à la compilation = polymorphisme static

**OVERLOADING** : Permet de déclarer deux méthode avec le même nom au sein d'une même classe. 
* Les paramètre de ses 2 méthodes doivent être différents : 
  * en nombre
  **OU**
  * en type 
  **OU**
  * en ordre de déclaration 

``` java
/*##########################################
  DIFFERENTIATION DES PARAMETRES : 3 cas : 
############################################ */
  
// 1. Nombre de paramètres 
add(int, int)
add(int, int, int)

// 2. Type de paramètres différent
add(int, int)
add(int, float)

// 3. Ordre de déclaration différent
add(int, float)
add(float, int)


/*###########################################
  EXEMPLE : NOMBRE DE PARAMETRE DIFFERENTS 
############################################# */

class DisplayOverloading
{
    public void disp(char c)
    {
         System.out.println(c);
    }
    public void disp(char c, int num)  
    {
         System.out.println(c + " "+num);
    }
}
class Sample
{
   public static void main(String args[])
   {
       DisplayOverloading obj = new DisplayOverloading();
       obj.disp('a');
       obj.disp('a',10);
   }
}



  ```
 


  method overloading is done by declaring same method with different parameters. The parameters must be different in either of these: number, sequence or types of parameters (or arguments). Lets see examples of each of these cases.
