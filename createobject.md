
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
