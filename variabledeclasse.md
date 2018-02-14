
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