
## Lecture des entrée claviers 

Les variables `String` sont enréalité des objets de type `Sting`. Ainsi pour que JAVA puisse lire ce que l'on tape au clavier on doit utiliser un objet de type `Scanner`
 
**= La lecture des entrées clavier se fait via l'objet `Scanner`.**
* Ce dernier se trouve dans le package java.util à importer. `import java.util.Scanner;`

Pour pouvoir récupérer ce vous allez taper dans la console, vous devrez initialiser l'objet `Scanner` avec l'entrée standard, `System.in`.

``` java
Scanner sc = new Scanner(System.in);
```

Il y a une méthode de récupération de données pour chaque type (sauf les `char`) : `nextLine()` pour les `String`, `nextInt()` pour les `int` ...

``` java
/*
#####################################
RECUPERATION DE LA SAISIE AU CLAVIER
#####################################
*/
Scanner sc = new Scanner(System.in);
System.out.println("Veuillez saisir un mot :");
String str = sc.nextLine();
System.out.println("Vous avez saisi : " + str);

/*
########################################
RECUPERATION DE LA SAISIE DE TYPE `CHAR`
########################################
*/
System.out.println("Saisissez une lettre :");
Scanner sc = new Scanner(System.in);

// On récupère une chaine de caractère
String str = sc.nextLine();

// On utilise la méthode 'charAt()' de l'objet 'String' pour récupérer le premier caratère
char carac = str.charAt(0);
System.out.println("Vous avez saisi le caractère : " + carac);
```

ATTENTION : la méthode `nextline()` récupère le contenu de toute la ligne et replace la tête de lecture au début d'une autre ligne 
```java

/*
###################################################
                    PROBLEME
###################################################
*/
import java.util.Scanner;

public class Main {
  public static void main(String[] args){
    Scanner sc = new Scanner(System.in);
    System.out.println("Saisissez un entier : ");
    int i = sc.nextInt();
    System.out.println("Saisissez une chaîne : ");
    String str = sc.nextLine();      
    System.out.println("FIN ! ");
   }
}

// … ne vous demandera pas de saisir une chaîne et affichera directement « Fin ». Pour pallier ce problème, il suffit de vider la ligne après les instructions ne le faisant pas automatiquement :

/*
###################################################
                    SOLUTION 
###################################################
*/
import java.util.Scanner;

public class Main {
  public static void main(String[] args){
    Scanner sc = new Scanner(System.in);
    System.out.println("Saisissez un entier : ");
    int i = sc.nextInt();
    System.out.println("Saisissez une chaîne : ");
    //On vide la ligne avant d'en lire une autre
    sc.nextLine();
    String str = sc.nextLine();      
    System.out.println("FIN ! ");
  }
}
```