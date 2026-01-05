# Forme normale

## Normalisation

La **normalisation** d'un [[schema de base de donnée relationnel]] est un processus qui consiste à analyser les différentes [[relation]] en se basant sur leur [[dépendance fonctionnelle]] et leur clé primaire afin de limiter la redondance et d'éviter les [[anomalie]] en se basant sur les [[#Forme normale]]. 

==/!\\==: L'utilisation de forme normale n'implique pas forcément un bon design de base de donnée 

## Forme normale

Une **forme normale** caractérise le fait qu'une [[relation]] respecte certaines contraintes. 

On distingue plusieurs forme normales :
- [[#1NF 1ere forme normale]]
- [[#2NF 2eme forme normale]]
- [[#3NF 3eme forme normale]]
- [[#FNBC Forme normale de Boyce-Codd]]

La forme normale d'une relation correspond au plus haut niveau de forme normale à laquelle la relations obéit avec chaque forme se basant sur la forme précédente

### 1NF : 1ere forme normale

La premiere forme normale **1NF** nous dit que tous les [[attribut]] doivent être des [[attribut#Attribut simple - composite|attribut simple]]

exemple : Si on prend un table commande ressemblant à ceci 

|IdCommande|Client|ProduitsCommandés|
|---|---|---|
|1|Dupont|Livre, Stylo, Cahier|
|2|Martin|Classeur, Crayon|

On remarque que la colonne `ProduitsCommandés` contient plusieurs valeurs par tuple ce qui crée les problèmes suivant :

- Cela rend la recherche par produit compliqué 
- Rajouté/supprimé un produit à une commande est compliqué

On peut résoudre ce soucis en appliquant la 1NF qui consiste à utiliser des valeurs atomique pour chaque attribut. Pour cela on dire que l'attribut `ProduitCommandés` ne peut contenir qu'une seule valeur, qu'un seul produit

On se retrouve alors avec le format suivant :

|IdCommande|Client|Produit|
|---|---|---|
|1|Dupont|Livre|
|1|Dupont|Stylo|
|1|Dupont|Cahier|
|2|Martin|Classeur|
|2|Martin|Crayon|
En faisant cela si on vaut ajouter ou supprimé un produit on peut supprimer ou ajouter un nouveau tuple. De plus cela simplifie grandement la recherche de commande par produit
### 2NF : 2eme forme normale

La seconde forme normale **2NF** se base sur la [[dépendance fonctionnelle#Dépendance fonctionnelle complète|dépendance fonctionnelle complète]]. La seconde forme normale nous dit que tous les attributs d'une relation $R$ qui ne font pas partie de la [[attribut#Clé|clé]] sont complétement dépendant de l'ensemble des attributs composant la clé.

En d'autre terme pour déterminer les attributs d'une relation on ne peut pas utiliser un sous ensemble de la clé

exemple : Si on reprend notre exemple de notre table commande corrigé et que l'on souhaite ajouter en plus le prix du produit ainsi que la date de la commande on se retrouve avec notre nouvelle relation qui ressemble à ceci 

| IdCommande | Client | Produit  | PrixProduit | DateCommande |
| ---------- | ------ | -------- | ----------- | ------------ |
| 1          | Dupont | Livre    | 25€         | 10/01/2023   |
| 1          | Dupont | Stylo    | 3€          | 10/01/2023   |
| 2          | Martin | Classeur | 7€          | 15/01/2023   |
Dans cette relation on dit que la clé est le couple `idCommande` et `Produit`

On remarque que l'attribut `PrixProduit` ne dépend que de `Produit`. 

Le problème de cette relation c'est la redondance de données que l'on va obtenir sur le prix du produit. En effet pour chaque produit on devra venir écrire le prix.
De plus si le prix du produit vient à changer alors on devra venir modifier chaque tuple de la relation ce qui peut augmenter le temps d'exécution du query ou créé des anomalie de mise à jour

Pour résoudre cela il est intéressant de retirer le prix du produit de la relation et de le définir dans une autre relations `Produits` afin de l'avoir qu'a une seule place. Cela nous donnerai les relations suivantes 

`Commandes`

| IdCommande | Produit  |
| ---------- | -------- |
| 1          | Livre    |
| 1          | Stylo    |
| 2          | Classeur |

`Produits`

Table "Produits" :

| Produit | PrixProduit |
|---------|-------------|
| Livre | 25€ |
| Stylo | 3€ |
| Classeur | 7€ |

### 3NF : 3eme forme normale

La troisième forme normale **3NF** se base sur la [[dépendance fonctionnelle#Transitivité fonctionnelle|transitivité fonctionelle]]. Elle nous dit que chaque attribut de la relation $R$ qui ne fait pas partie d'une [[attribut#Clé|clé]] est directement dépendant d'une clé

Autrement dit un ensemble d'attribut $Y$ est forcément dépendant d'un ensemble $X$ qui correspond a une  clé et ne peut pas être dépendant d'un autre ensemble $Z$ qui n'est pas égale $X$

On peut aussi dire que tous les attributs dépendent de la clé et uniquement de la clé

exemple : Soit la relation EMPLOYE suivante ayant pour clé `idEmployé`

| IdEmployé | Nom | Département | ResponsableDépartement |
|-----------|-----|-------------|------------------------|
| 1 | Dubois | Informatique | Moreau |
| 2 | Leroy | Marketing | Petit |
| 3 | Thomas | Informatique | Moreau |
On remarque que l'attribut `ResponsableDepartement` dépend du `Département` et non de la clé or si un responsable change c'est plusieurs tuple qui doivent être mise à jour. De plus cela crée de la redondance de données car on peut avoir le même responsable de département à insérer plusieurs fois. 
Enfin cela peut crée des incohérence si on se trompe de responsable

Pour résoudre ce problème il vaudrait mieux séparer l'attribut ` ResponsableDépartement` dans une autre relation. On aurai donc ceci

Table "Employés" :

| IdEmployé | Nom | Département |
|-----------|-----|-------------|
| 1 | Dubois | Informatique |
| 2 | Leroy | Marketing |
| 3 | Thomas | Informatique |


Table "Départements" :

| Département | ResponsableDépartement |
|-------------|------------------------|
| Informatique | Moreau |
| Marketing | Petit |



### FNBC :  Forme normale de Boyce-Codd

La **forme normal  de Boyce-Codd** **FNBC** est une forme normale qui étend la [[#3NF 3eme forme normale|3NF]] en rajoutant comme condition que l'ensemble d'attribut $X$ dont l'ensemble d'attribut $Y$ dépend est forcément la [[attribut#Attribut#Super clé|super-clé]] de la relation


### 4NF : 4eme forme normale

La quatrième forme normale **4NF** se base sur la [[dépendances multivaluées]]. Elle nous dit la chose suivante :

Une relation $R$ est en quatrième forme si elle est en [[#FNBC Forme normale de Boyce-Codd|FNBC]] et si pour toute [[dépendances multivaluées#Dépendance multivaluées trivial / non trivial|dépendance multivaluées non trivial]] $X$ est une super-clé de $R$

exemple : Soit une relation $COURS(etudiant, cours,textbook)$ qui répertorie l'ensembles des cours d'un étudiant on peut avoir 

| étudiant | cours | textbook      |
| -------- | ----- | ------------- |
| John     | Math  | algèbre       |
| John     | CS    | programmation |
| Jhon     | Math  | statistique   |
| John     | CS    | Algorithme    |
On remarque que l'on à de la redondance car pour chaque cours on à une ligne en fonction du livre pour la passer en 4NF il faudrait limiter cela en séparant les information comme ceci en 2 relations

Une relations $COURS(étudiant,cours)$

| étudiant | cours |
| -------- | ----- |
| John     | Math  |
| John     | CS    |

Une relation $TEXTBOOK(cours,textbook)$

| cours | textbook      |
| ----- | ------------- |
| Math  | algèbre       |
| CS    | programmation |
| Math  | statistique   |
| CS    | Algorithme    |
