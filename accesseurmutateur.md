
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