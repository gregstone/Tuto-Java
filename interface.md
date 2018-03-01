## Les interfaces 

[interface VS abstract class : définitions et différences](https://www.youtube.com/watch?v=mf0jQijo9C4)


* Dans une interface toutes les méthodes sont par défaut abstraite et public 

* **L'interface est comme un contrat.** 

Afin de pouvoir créer une banque, on écrit en amont un contrat qui définit l'ensemble des services minimums obligatoires afin que celle ci puisse être considérée comme une 'banque'
> une banque doit permettre le retrait d'argent 
> une banque doit permettre le dépot d'argent... 

L'ensemble des services obligatoire sont définit comme des méthodes vide au sein d'une interface `bank`

lorsqu'on voudra créer une nouvelle banque `caIdf` on devra implémenter (`implements`) l'interface `bank` et définir les détails pour l'ensemble des méthodes. On devra définir la manière dont notre banque réalisera les différents services obligatoires. 

L'interface permet de s'assurer que notre banque disposera bien d'un minimum de services obligatoires, sans pour autant nous dire comment les mettre en oeuvre. 

Ainsi chaque banque peut réaliser les différents services comme elle le souhaite. 

``` java
/* 
############################################
        CREATION D'UNE INTERFACE 
############################################
*/

public interface bank {
  // définit l'ensemble des méthodes 
  void retrait();
  void dépôt(); 
  ...
}

/*
#############################################
        UTILISATION D'UNE INTERFACE 
#############################################
*/ 
public class caIDF implements bank {
  // la classe caIdf impléments l'interface 'bank'
  // l'ensemble des méthodes de l'interface `bank` doivent être définit ici 


}

```

* Permet de bénéficier 'd'héritage multiples'

# Interface depuis JAVA 8 

* Possible de définir des méthodes par defaut 
* Toutes les méthodes ne sont plus forcément abstraites / peuvent désormais contenir des méthodes statiques

``` java 
public interface Mitose extends Reproduction {
	public static void description() {
		Reproduction.description();
		System.out.println("Redéfinie dans Mitose.java");
	}
	
	default void reproduire() {
		System.out.println("Je me divise !");
	}
}

public interface Pondre extends Reproduction {

	public static void description() {
		Reproduction.description();
		System.out.println("Redéfinie dans Pondre.java");
	}

	
	default void reproduire() {
		System.out.println("Je ponds des oeufs !");
	}
	
}

public class Alien implements Pondre, Mitose {

	public void reproduire() {
		
		System.out.println("Je suis un alien et :");
		Pondre.super.reproduire();
		Mitose.super.reproduire();

	}
}
```
> Le comportement par défaut permet de définir des méthodes dans l'interface sans devoir obligatoirement les définir dans les classe qui en hérite. 