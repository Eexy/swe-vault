## Spécialisation

La **spécialisation** est le processus qui défini un ensemble de sous-classe d'une [[entité]]. Cet ensemble est défini sur la base d'une caractéristique différenciant. L'entité de départ devient alors la **super-classe**

exemple : La spécialisation {`SECRETAIRE`, `INGENIEUR` } de l'entité EMPLOYE se fait sur la propriété `job_type`

Il faut prendre en compte qu'il peut existé plusieurs spécialisation pour la même super classe

exemple : Il existe une spécialisation sur la propriété `job_type` qui nous donne la spécialisation {`SECRETAIRE`, `INGENIEUR`} mais il peut aussi existé une spécialisation {`EMPLOYE_SALARIE`, `EMPLOYE_A_L'HEURE` }

## Généralisation

La **généralisation** est le processus de suppression des différence entre plusieurs [[entité]] afin d'en faire une super-classe. Dans ce processus les entité de départ deviennent alors les sous-classe de la nouvelle super-classe

## Contrainte

Les sujet suivant s'applique aussi bien au sous-classe qu'au super classe. Les contraintes vont permettre de définir les conditions pour qu'une instance d'une entité appartienne à une sous-classe

### Contrainte sur attribut

Dans certaines spécialisation on peut déterminé les instance d'entités qui vont devenir des membre des sous-classe en utilisant une condition sur un attribut. Ont dit ainsi que la sous-classe est défini par prédicat

exemple : tout les entités employé dont l'attribut `job_type=secretary` font parties de la sous-classe SECRÉTAIRE

Dans le cas où toutes les sous-classe de la spécialisation se base sur le même attribut de la super-classe alors la spécialisation elle est est appelé **spécialisation sur attribut**

### Contrainte par utilisateur

S'il n'y pas de condition de participation pour qu'une entité appartiennent à une sous-classe alors ont dit qu'elle est défini par utilisateur.

Dans ce cas-ci cela se fera en fonction des opérations effectué
### Contrainte par disjonction

Cette contrainte indique que les sous-classe de la disjonction d'une même spécialisation doivent être des ensemble distinct. Cela veut tout simplement dire que les entités peuvent appartenir au maximum à une seule sous-classe

Une contrainte sur attribut implique forcément une contrainte par disjonction. Attention cela ne concerne que le cas où l'attribut sur lequel la contrainte est effectué est un [[attribut#Attribut simple - composite|attribut simple]]

La représentation graphique d'une contrainte par disjonction est un cercle avec un $d$

![[subclass.png]]


Dans le cas ou plusieurs sous-classe peuvent partager les même entité alors ont dit quelles se chevauchent.

La représentation graphique d'un chevauchement est représenté par un $o$

![[overlapping.png]]

### Contrainte par complétude

![[Pasted image 20250316140541.png]]

#### Complétude total

Une contrainte par complétude total signifie que chaque entité appartenant à la super-classe doit aussi appartenir au moins à une sous-classe

exemple : l'entité EMPLOYE doit appartenir sous à la sous-classe EMPLOYÉ_SALARIE ou EMPLOYE_A_L'HEURE

La représentation graphique d'une contrainte par complétude total correspond à deux ligne connectant l'entité au cercle

#### Complétude partial

Une contrainte par complétude partial indique que chaque entité de la super classe n'est pas obligé d'appartenir à une sous-classe.

Cette contrainte est représenté par une ligne connectant la super-classe au cercle

Exemple : L'entité EMPLOYÉ n'appartient pas forcément à la sous-classe SECRÉTAIRE


