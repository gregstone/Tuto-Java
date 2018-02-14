## Les tableaux 

### Tableau à une dimmension
* Il existe autant de tableau que de type de variable 
* Chaque tableau à un type donné et ne peut donc accepter que les variables de ce type

``` java
/*
###################################################
                    SYNTAX 
###################################################
*/
<type du tableau> <nom du tableau> [] = { <contenu du tableau>};

/*
###################################################
                    EXEMPLE 
###################################################
*/
int tableauEntier[] = {0,1,2,3,4,5,6,7,8,9};
double tableauDouble[] = {0.0,1.0,2.0,3.0,4.0,5.0,6.0,7.0,8.0,9.0};
char tableauCaractere[] = {'a','b','c','d','e','f','g'};
String tableauChaine[] = {"chaine1", "chaine2", "chaine3" , "chaine4"};

/*
###################################################
            DECLARATION TABLEAU VIDE 
###################################################
*/
int tableauEntier[] = new int[6];
//Ou encore
int[] tableauEntier2 = new int[6];
// ici on initialise un tableau vide avec 6 cases
```
> **Tableau vide :** il faut impérativement indiquer le nombre d'éléments que contiendra le tableau

### Tableau multi dimentionnelle

**DEFINITION** : Tableau contenant au minimum 2 tableau

``` java
int premiersNombres[][] = { {0,2,4,6,8},{1,3,5,7,9} };
// tableau avec 2 lignes : 1 ligne avec {0,2,4,6,8}, une 2ème ligne avec {1,3,5,7,9}  
```
* `premiersNombres[0][0]` correspondra au premier élément de la ligne paire
* `premiersNombres[1][0]` correspondra au premier élément de la ligne impaire.
