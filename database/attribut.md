# Attribut

**attribut** : Un attribut est un propriété d'une [[entité]]. Chaque attribut possède une valeur

On distingue plusieurs type d'attributs : 
- simple - composite
- valeur unique - multiple
- sauvegardé - dérivé
- nullable

## Attribut simple - composite

Un **attribut composé** est un attribut qui peut lui même être divisé en plusieurs sous partie

exemple : un attribut adresses peut être divisé comme ceci
- nom de la rue
- numéro
- code postal
- ville

Un **attribut simple** est un attribut qui ne peut pas être divisé. On parle aussi d'attribut **atomique**

exemple : un attribut prénom ne peut pas être divisé en plusieurs sous partie

## Attribut à valeur unique - multiple

Un **attribut à valeur unique** est un attribut qui ne peut contenir qu'une seule valeur

exemple : un attribut âge ne contient qu'une seule valeurs

Un **attribut à valeur multiple** est un attribut qui possède un ensemble de valeurs

exemple : un attribut couleur sur une entité voiture peut posséder un ensemble de valeurs en fonction du nombre de couleurs présente

## Attribut sauvegardé - dérivé

Un **attribut sauvegardé** est simplement un attribut sauvegardé en BDD

exemple : l'attribut date de naissance d'une personne est sauvegardé en BDD

Un **attribut dérivé** est un attribut dérivé à partir d'un autre attribut voir d'une autre entité associé

exemple :  l'attribut âge peut être obtenu via la date de naissance

## Attribut nullable

Un **attribut nullable** est un attribut qui peut ne pas avoir de valeur

exemple : l'attribut numéro d'appartement peut être null si la personne vie dans une maison

## Clé

Une **clé** est un attribut ou un ensemble d'attribut dont la valeurs est unique pour chaque entité. Cette clé va permettre d’identifié chaque entité de façon unique

exemple : Deux entreprises peuvent avoir le même nombre d'employés mais chaque entreprise possède un nom unique. Le nom est donc une clé de l'entité Entreprise

Dans certains cas c'est la combinaison de plusieurs attributs qui est utilisé en tant que clé

Enfin il peut y avoir plusieurs clé pour une même entité. 

exemple : Une entité voiture peut avoir comme clé son id et son numéro de plaque

### Super clé

Une clé est une super clé si on ne peut pas supprimer un attribut sans que cela cause la la clé perte son statut de clé. Autrement dit une super clé est la version minimal d'une clé

### Clé candidate

Si une entité possède plusieurs clé alors on parle de clé candidate pour chacune des clé

### Attribut premier

Un attribut est dit premier s'il fait partie d'une clé

## Ensemble de valeurs

Chaque attribut simple est associé avec avec un ensemble de valeurs possible, on parle de **domaines de valeurs**. 

exemple : Soit un attribut âge pouvant aller de 16-70 ans. On peut dire que son ensemble de valeur est l'ensemble des entiers allant de 16-70 ans

L'ensemble de valeur n'est généralement pas affiché sur le diagramme

Mathématiquement un attribut $A$ d'un ensemble d'entité $E$ dont l'ensemble de valeur est $V$ peut être défini en tant que fonction comme ceci :

$$
A : E \rightarrow P(V)
$$

On fait référence à la valeur d'un attribut $A$ pour une entité $e$ en tant que $A(e)$ 

Dans le cas d'un attribut $A$ qui est un attribut [[#Attribut simple - composite|composite]] son ensemble de valeur $V$ correspond au [[produit cartesien]] des ensemble de valeur de chaque attribut simple

$$
V = P(P(V_1)\times P(V_2)...\times P(V_n)
)$$