# Liste tuto 

## Programmation Objet – Bases Java

* Les bases en Java : l’IDE Eclipse, JDK… Comment utiliser Eclipse : [tuto openclassrooms](https://openclassrooms.com/courses/apprenez-a-programmer-en-java/installer-les-outils-de-developpement)  

* Les bases en Java : Variables, conditions, boucles… jusqu’au TP. TUTO ICI (continuer jusqu’au chapitre 6, TP) : [tuto openclassrooms suite](https://openclassrooms.com/courses/apprenez-a-programmer-en-java/installer-les-outils-de-developpement)  
* La programmation orientée objet (POO) en Java : [DEF POO](https://www.jmdoudoux.fr/java/dej/chap-poo.htm) ( Chapitre 4.1 à 4.6.6)

* Tutos Java Orienté Objet : [tuto openclassrooms suite](https://openclassrooms.com/courses/apprenez-a-programmer-en-java/installer-les-outils-de-developpement) (Chapitres 1 à 9)

## Programmation Web :

* Revoir les technos web (HTML 5, CSS 3, Javascript, JQuery, Bootstrap)

## Java EE :

* [Utilisation de Maven](http://www.mkyong.com/maven/how-to-create-a-java-project-with-maven/)

**Sprint Boot**

* [Quick start](https://projects.spring.io/spring-boot/)

* [Tuto Hello World](http://www.javainterviewpoint.com/spring-boot-hello-world-example-eclipse/)

* [Spring Boot - Maven - Eclipse](http://www.springboottutorial.com/creating-spring-boot-project-with-eclipse-and-maven)

* [Spring Boot - MVC / Web JSP](https://www.mkyong.com/spring-boot/spring-boot-hello-world-example-jsp/)

## Angular 4 :

* [TUTO 1](https://applyhead.com/angular-4-tutorial-make-angular-4-app-using-github-api/)

* [TUTO 2](https://medium.com/codingthesmartway-com-blog/angular-4-3-httpclient-accessing-rest-web-services-with-angular-2305b8fd654b)

## Introduction à SCRUM :

* [Introduction à SCRUM](https://www.agiliste.fr/introduction-methodes-agiles/)

---------------



# `next()`, `nextline()`


* Méthode de la classe `Scanner`

`next()` : 
* read the input only till the space. It can't read two words separated by a space. 
* next() places the cursor in the same line after reading the input.

`nextline()` : 
* reads input including space between the words (that is, it reads till the end of line \n). 
* Once the input is read, nextLine() positions the cursor in the next line.


# Comparaison des objets : Réfférences et contenu 

Ne pas confondre la référence d'un objet et son contenu, si on ecrit 
``` java
// Créer automatiquement un objet (Inutile d'uitliser New....)
String chaine1 = "bonjour";

// Deuxième objet de type String = on doit utiliser New 
String chaine2 = "bonjour";
l
chaine1 == chaine2 // retourne true car on réalise une comparaison sur les références des instances. (cf. commentaire 3)  
```
> `chaine1` créer automatiquement un objet de type `String` sans que l'on ai besoin d'écrire `Sting chaine1 = new String();`

> `chaine2` constituant un deuxième  objet de type `String` on doit utiliser le mot clé `New` pour créer un nouvel objet `String` `Sting chaine1 = new String();`
> Dans l'exemple on n'utilise pas `New` pour `chaine2`: ainsi `chaine1` et `chaine2` possèdent la même réfférence (on a pas créer de deuxième objet). 


# `this`
``` java 
private int nombre;
public maclasse(int nombre) {
    nombre = nombre; 
    // variable de classe = variable en paramètre du constructeur

    // il est préférable de préfixer la variable d'instance par `this`

    this.nombre = nombre;
}
```
# `instanceof`

Permet de vérifier que l'objet est bien une instance d'une classe donnée. 

# `synchronized()`

The synchronized keyword is all about different threads reading and writing to the same variables, objects and resources. This is not a trivial topic in Java, but here is a quote from Sun:

    "synchronized methods enable a simple strategy for preventing thread interference and memory consistency errors: if an object is visible to more than one thread, all reads or writes to that object's variables are done through synchronized methods."

**In a very, very small nutshell:** 

When you have two threads that are reading and writing to the same 'resource', say a variable named foo, you need to ensure that these threads access the variable in an atomic way. Without the synchronized keyword, your thread 1 may not see the change thread 2 made to foo, or worse, it may only be half changed. This would not be what you logically expect.


# `final`

`final` = `const` en Js

# Modificateurs 

Modificateur	Rôle

**public** la méthode est accessible aux méthodes des autres classes

**private**	l'usage de la méthode est réservé aux autres méthodes de la même classe

**protected**	la méthode ne peut être invoquée que par des méthodes de la classe ou de ses sous-classes

**final** la méthode ne peut être modifiée (redéfinition lors de l'héritage interdite)

**static** la méthode appartient simultanément à tous les objets de la classe (comme une constante déclarée à l'intérieur de la classe). Il est inutile d'instancier la classe pour appeler la méthode mais la méthode ne peut pas manipuler de variable d'instance. Elle ne peut utiliser que des variables de classes.

**synchronized** la méthode fait partie d'un thread. Lorsqu'elle est appelée, elle barre l'accès à son instance. L'instance est à nouveau libérée à la fin de son exécution.

**native** le code source de la méthode est écrit dans un autre langage

**Sans modificateur, la méthode peut être appelée par toutes autres méthodes des classes du package auquel appartient la classe.**

# Les constructeurs 

La déclaration d'un objet est suivie d'une sorte d'initialisation par le moyen d'une méthode particulière appelée constructeur pour que les variables aient une valeur de départ.

Les constructeurs sont systématiquements invoqué à la création de l'objet (et uniquement à la création de l'objet. Les constrcuteur ne osnt plus appelés par la site. 

Le constructeur suit la définition des autres méthodes excepté que son nom doit obligatoirement correspondre à celui de la classe et qu'il n'est pas typé, pas même void, donc il ne peut pas y avoir d'instruction return dans un constructeur. On peut surcharger un constructeur.

La définition d'un constructeur est facultative. Si aucun constructeur n'est explicitement défini dans la classe, le compilateur va créer un constructeur par défaut sans argument. Dès qu'un constructeur est explicitement défini, le compilateur considère que le programmeur prend en charge la création des constructeurs et que le mécanisme par défaut, qui correspond à un constructeur sans paramètres, n'est pas mis en oeuvre. Si on souhaite maintenir ce mécanisme, il faut définir explicitement un constructeur sans paramètres en plus des autres constructeurs.

## Constructeur simple

* Ne nécessite pas de définition explicite : son existence découle automatiquement de la définition de la classe. 

```java
public MaClasse() {}
```

## Constructeur avec initialisation fixe

* Permet de créer un constructeur par défaut  

```java
public MaClasse() {
    nombre = 5;
}
```

## Constructeur avec initialisation des variables 

* Permet de spécifier les valeurs des données à initialiser.    

```java
public MaClasse(int valeur) {
    nombre = valeur;
}
```

# Destructeur = `fianlize()`

Un destructeur permet d'exécuter du code lors de la libération, par le garbage collector, de l'espace mémoire occupé par l'objet. En Java, les destructeurs appelés finaliseurs (finalizers), sont automatiquement invoqués par le garbage collector.

Pour créer un finaliseur, il faut redéfinir la méthode finalize() héritée de la classe Object.

