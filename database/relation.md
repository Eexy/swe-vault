# Relation

Une relation correspond à un ensemble d'attribut lié entre eux représentant une [[entité]] du monde réel. Les relations sont représenté par une **table**. Chaque ligne de la table correspond à une entité du monde réel. Cela permet aussi de représenté une [[association]]

exemple : Une table ETUDIANT contient plusieurs ligne, chaque ligne correspond à un étudiant du monde réel. On va par exemple retrouvé les colonnes pour :
- le nom
- le prénom
- numéro d'étudiant
- ...

## Schéma de relation

Un **schéma de relation** décrit une [[#Relation]] :

$$
R(A_1, A_2,...,A_n)
$$
Ou on à :
- $R$ est le nom de la relation
- $A_i$ est un [[#Attribut]]. C'est le nom donné au [[#Domaine]] dans la relation courante

Chaque attribut correspond à un domaine $D$. $D$ est alors de domaine de $A_i$ qui peut être écrit $dom(A_i)$

## Degré

 Une [[#Relation]] possède un **degré** qui correspond au nombre d'[[#Attribut]] qui la compose
 
## Domaine

Un **domaine** $D$ est une ensemble de valeur **atomique**. Cela veut dire que chaque valeur du domaine est indivisible.

Un moyen de créer un domaine est de spécifié le type de donné (aussi appelé **format**) du quel les valeurs du domaine sont extraite. Il est utile de donné un nom au domaine afin d'interpréter les valeurs

exemple : Le domaine $nom$ correspond à l'ensemble des chaîne de caractère représentant un nom

## Attribut

Un **attribut** $A_i$ correspond au rôle joué par le [[#Domaine]] dans la relation courante. $D$ est alors le domaine de $A_i$. Il est noté 

$$
dom(A_i)
$$
## Etat de relation

Un **etat de relation** $r$ d'un schéma $R(A_1,...,A_n)$ est noté 

$$
r(R)
$$
est un ensemble de $n$-[[#Tuple]] tel que 

$$
r = {t_1, t_2,...,t_n}
$$
Il permet de représenter une relation $R$ à un instant T

## Tuple

Dans le model relationnel un **tuple** correspondant à une liste de $n$ valeurs ordonné tel qu'on à 

$$
t = <v_1, v_2,...,v_n>
$$
Ou chaque valeur $v_i$ est un élément de $dom(A_i)$ ou bien la valeur NULL. 

On fait réference à la $i$-eme valeur du tuple $t$ qui correspond à l'[[#Attribut]] $A_i$ via la notation : $t[A_i]$ 



## Représentation mathématique

Une [[#Etat de relation]] $r(R)$ est une [[relation mathematique]] de dégrée $n$ sur les domaine $dom(A_i)$. C'est donc un [[sous-ensemble]] du [[produit cartesien]] sur les domaines qui définisse $R$

$$
r(R) \subseteq (dom(A_1) \times dom(A_2) \times ... dom(A_n))
$$

