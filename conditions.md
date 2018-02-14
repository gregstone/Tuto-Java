## lES CONDITIONS 

### Le switch 

``` java 
/*
###################################################
                    SYNTAX 
###################################################
*/
switch (/*Variable*/)
{
  case /*Argument*/:
    /*Action*/;
    break;        
  default:
    /*Action*/;             
}
```
> 1. La classe évalue l'expression figurant après le switch (ici /*Variable*/).
> 2. **SI** la première languette (`case /*Valeur possible de la variable`) correspond à la valeur de `/*Variable*/`, l'instruction figurant dans celle-ci sera exécutée.
> 3. **SINON**, on passe à la languette suivante, et ainsi de suite.
> 4. Si aucun des cas ne correspond, la classe va exécuter ce qui se trouve dans l'instruction default:/*Action*/;
> `break` permet de sortir du switch si une condituition correspond (mettre un `break` après chaque `case`)
