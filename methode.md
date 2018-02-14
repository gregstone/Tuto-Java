
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