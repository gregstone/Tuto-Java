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