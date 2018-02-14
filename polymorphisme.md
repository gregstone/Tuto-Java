
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