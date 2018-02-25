# TUTO JAVA - COURSERA 

[tuto coursera](https://www.coursera.org/learn/programmation-orientee-objet-java/home/welcome)

# Heritage `extends`

video 14

**Enrichissement** = Ajout d'attributs ou de méthodes par la sous classe
**Spécialiser** = Redéfinition d'attributs ou de méthode de la super classe par la sous classe

* L'héritage permet de représenter la relation `est-un`
    * Super classe : Personnage 
    * Sous classe : Guerrier 
    > un `Guerrier` **EST UN** `Personnage`

* la relation `a-un` représente l'encapsulation 
    * Sous classe : Guerrier. A l'intérieur de cette sous classe on définit une nouvelle méthode `Sabre`
    > un `Guerrier` **A UN** `Sabre`
    > La méthode `sabre` est donc encapsulé à l'interieure de la classe `Guerrier
    
    `
# Heritage : `protected` 

vidéo  15

* Une sous classe n'a pas accès au variable `private` hérité de sa super classe
* pour permettre l'accès à ces variables on utilise `protected`

* Les varaibles / méthodes déclaré `protected` sont accessible : 
    * aux sous classes héritant de la super classe 
    * à toutes les autres classes situés dans le même package

En dehors de ces deux cas (classe hérité, classe situé dans le même package) les éléments déclarés `protected` agit comme le type `private`

# Masquage / Redefinition 

video 16 

**Masquage** (pour les variables = shadowing) : un nom de variable identique dans la super classe et dans la sous classe. La varaible de sous classe masque alors la varaible de super classe   

**Redéfinition** (méthodes = overriding): Méthode déjà définit dans une super classe qui a une nouvelle définition dans une sous classe. 
* les méthodes rédéfinit (**= méthodes spéclialisées**) on la priorité sur les méthodes de la super classe
* Si on souhaite appelé dans la sous classe la méthode de la super classe et non pas la méthode redéfinit on utilise le mot clés `super`

``` java
// SUPER CLASSE 
public class Personnage {
    // METHODE RENCONTRER PAR DEFAUT 
    public void rencontrer(){
        System.out.println("Bonjour");
    }
}

// CLASSE HERITE
public class Guerrier extends personnage {
    //METHODE RENCONTRER SPECIALISE 
    public void rencontrer(){
        super.rencontrer() // appel la méthode par défaut 
        System.out.println("Je suis un guerrier");
    }
}
```
> l'appel de la méthode par defaut dans la méthode spécialisé permet de retourner `Bonjour` avant d'afficher `Je suis un guerrier

# Heritage des constructeurs 

vidéo 17 

Dans une classe hérité on doit redéclarer les constructeurs de la super classe. Cela permet de pouvoir utiliser l'ensemble des variables de la super classe dans la sous classe. 

Pour hériter des constructeur de la super classe dans une sous classe on utilise le mot clé `super`

``` java 
// SUPER CLASSE
class FigureGeometrique {
    private Position position; 
    // constructeur de la super classe
    public FigureGeometrique(double x , double y) {
        position = new Position(x, y);
    }
}

// SOUS CLASSE
class Rectangle extends FigureGeometrique {
    private double largeur;
    private double hauteur; 
    // constructeur de la sous classe 
    // prend en paramètre `x` et `y` de la super classe + `l` et `h` de la sous classe
    public Rectangle(double x , double y , double l, double h ) {
        super(x,y); // Hértiage du constructeur de la super classe dans la sous classe 
        largeur = l; 
        hauteur = h;
    }
}
```
> On à recours à `super` uniquement lorque le constructeur de la super classe prend des paramêtre 
> Si le constructeur de la super classe est uniquement le constructeur par défaut, l'utilisation de `super` n'est pas nécessaire

**L'utilisation de `super` dans les constructeur de la sous classe doit impérativement constituer le premier éléments à écrire**

# Polymorphisme : Résolution dynamique 

vidéo 18

Le polymorphisme ets le fait que les instances d'une sous classe gardent leurs méthodes propres. Le choix des méthodes à invoqués ce fait lors de l'éxecution du programmeen fonction de la nature réelles des instances concernés (cf. héritage et résolution dynamique des liens)

Exemple : 
* Super classe = `Personnage`
    * comporte une méthode `rencontrer()` par défaut
* Sous classe = `Sorcier`...
* Sous classe = `Guerrier`,
    * comporte une méthode `rencontrer()` spécialisé

ON VEUT 
* que chaque personnage réalise l'action `rencontrer()` = on veut que les personnages spécifiques rencontre le personnage générale
    * Cette action est différente pour le `Sorcier` et le `Guerrier`

ON CREER 
* Un tableau de `Personnage` contenant chaque type de personnage 

```java 

public static void main(String[] args) {
    Personnage lePersonnage = new Personnage();
    
    // on cérer un tableau contenant nos deux personnages spécifiques
    Personnage[] personnages = new Personnage[2]; 

    // On remplis le tableau avec nos personnages
    personages[0] = new Sorcier();
    personages[1] = new Guerrier();
    
    for (int 0 ; i< personnages.length ; ++i) {
        personnages[i].rencontrer(lePersonnage);
    }
}
```
> Ici on met des objets de type `Sorcier` et `Guerrier` dans un tableau de type `Personnage` // **Normallement en java lors d'une affectation, tout les éléments situé à droite doivent être du même type que ceux situé à gauche** 

Dans notre cas cela est tout de même possible car les objets `Sorcier` et `Guerrier` hériote de la classe `Personnage`

Sachant que l'on stocke un objet de type `Guerrier` dans un variable de type `Personnage` quel action sera exécuté à l'appel de la méthode `rencontrer()`
* La méthode `erencontrer()` par defaut (definit dans la classe `Personnage` OU la méthode `rencontrer()` spécialisé (redéfinit dans la classe `Guerrier`)

Il existe de ca possible pour résoudre ce problèmes 
1. **RESOLUTION STATIQUE** : Le type de la variable détermine la méthode choisit
> (ici variable  nommé `personnages` de type `Personnage`, c'est donc la méthode `rencontrer()` de la classe `Personnage` qui est appliqué).  
> on parle egalement de type apparent
2. **RESOLUTION DYNAMIQUE** :  Le type de l'objet stocké dans la variable détermine la méthode choisit
> ici un objet de type `Guerrier` , c'est donc la méthode `rencontrer()` de la classe `Guerrier` qui est appliqué.
> on parle egalement de type effectif

# Méthodes abstraites 

* Non définit dans la classe ou elle est introduite (super classe) 
* Oblige l'ensembles des sous classes à en définir le contenu  
* Une méthode abstraite doit être contenu dans une classe abstraite 
* Une classe abstraite ne oeut pas être instancié 

``` java
// super classe abstraite 
abstract class Personnage {

    // méthode abstraite 
    public abstract void afficher() {

    }
}
```

* Les sous classe qui hérite d'une classe abstraite restent abstraite tant qu'elles n'on pas rédéfinit l'ensembles des méthodes abstraites dont elles ont hérités 