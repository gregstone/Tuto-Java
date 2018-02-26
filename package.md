# Package 

Regroupement de classes voisines ou qui couvrent un même domaine 

### LES PACKAGES 

#### Création d'un package

* Nom tout en minuscule 
* Caractères autorisés : de a à z, de 0 à 9 et peuvent contenir des points (.) ;
* tout package doit commencer par com, edu, gov, mil, net, org ou les deux lettres identifiant un pays (ISO Standard 3166, 1981) ; « fr » correspond à la France, « en » correspond à l'Angleterre (pour England)etc.
* aucun mot clé Java ne doit être présent dans le nom, sauf si vous le faites suivre d'un underscore (« _ »), comme ceci : com.sdz.package_. 

ex: `com.package.test`

**Les classes contenues dans un package ont en toute première instruction la déclaration de ce package**
```java
package com.sdz.test;

public class A {
  public B b = new B();
}
```

* Un package est un ensemble de dossiers et de sous-dossiers.
* Si vous voulez utiliser un mot clé Java dans le nom de votre package, vous devez le faire suivre d'un underscore (« _ »).
* **Les classes déclarées public sont visibles depuis l'extérieur du package qui les contient.**
* **Les classes n'ayant pas été déclarées public ne sont pas visibles depuis l'extérieur du package qui les contient.**
* Si une classe déclarée public dans son package a une variable d'un type ayant une portée default, cette dernière ne pourra pas être modifiée depuis l'extérieur de son package.
