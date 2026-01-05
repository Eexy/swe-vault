# Règle de design informel

Les **règles de design informel** sont des [[règle de design]] qui sont plutôt des guidelines qu'il est conseillé de suivre mais dont il peut être nécessaire d'outrepasser

## Avoir une sémantique claire

La première règle qui est conseillé de suivre est d'avoir une sémantique claire pour quà la lecture du [[ER model]] par exemple l'utilisateur comprenne rapidement le sens et le but de notre [[base de donnée]]. Cela passe par :

1. Choisir de bon nom pour les [[relation]]
2. Choisir de bon nom pour les [[relation#Attribut|attribut]]
3. Évité de mélanger plusieurs [[entité]] dans la même relation

## Eviter les information redondante

Un bon design de base de donné a pour but d'en plus représenter le monde réel le plus fidèlement de minimiser l'espace de stockage nécessaire.

Pour limiter le stockage il est important d’éviter les informations redondante. Par exemple si on prend le cas d'une base de donnée qui est censé représenter une entreprise où chaque employé travaille dans un département.

Il est mieux de séparer les deux entités et de simplement relié l'employé à un département simplement en prévoyant une clé étrangère dans la table employé qui serai l'identifiant pour récurer le département plutôt qu'à chaque fois devoir insérer les informations du département dans la table employé.

De plus cela limite les [[anomalie]]

## Eviter les NULL

Si une relations regroupe plusieurs attributs on peut se retrouver dans le cas où plusieurs des tuples de la relations possèdent des valeurs NULL. Plus le nombre de tuple augmente plus ont augmente l'espace nécessaire pour ses tuples pour des informations dont ils n'ont besoin.

De plus cela peut créer des problème lors des jointures. Il est alors conseillé de réduire au maximum le nombre de valeur NULL possible dans une relation. Cela peut par exemple se faire en créant de plus petite relations en partant de la relations d'origine. 

Dans le cas où on ne peut pas faire cela alors il est important que l'utilisation du NULL s'applique sur des cas exceptionnels

## Utiliser des paire clé étrangère/clé primaire

Lorsque l'on associe deux relations il est nécessaire que l'association se fasse sur des paire clé primaire / clé étrangère. Cela permet de s'assurer que la jointure se fera correctement et que chaque tuple sera associé à un tuple existant mais cela permet aussi d'éviter la création de faux tuple

Par exemple si l'association se fait sur d'autre clé lors d'un migration qui aurai pour but de fusionner deux relations A et B on pourrai se retrouver avec de nouveau tuple qui ne sont ni dans A ni dans B qui sont créé