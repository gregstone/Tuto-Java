
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
