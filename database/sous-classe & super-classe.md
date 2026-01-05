# Sous-classe & super-classe


Une **sous-classe** correspond à une sous-entité d'une [[entité]] possédant un sens particulier. 

exemple : Une entité SECRÉTAIRE est une sous-classe de l'entité EMPLOYÉ

Dans l'exemple ci-dessus l'entité EMPLOYÉ est appelé la **super classe** de l'entité SECRÉTAIRE

Une sous-classe *hérite* toujours de tous les [[attribut]] de sa super-classe mais peut posséder d'autre attribut en plus

exemple : l'entité secrétaire possède toutes les caractéristique d'un employée mais peut avoir une propriété `vitesse de frappe`

Il en va de même des relations. Ainsi une sous classe *hérite* des relations de la super-classe mais peut aussi avoir ses propre relation

## Représentation graphique

![[subclass.png]]

Les super-classe et les sous-classe sont des entités ainsi elles suivent la même représentation qu'une entité "normale"

le cercle avec un "d" représente une [[specialisation - généralisation#Contrainte par disjonction|contrainte par disjonction]]


