# Association

## Type de relation, ensemble et instance

Un **type d'association** $R$ parmi $n$ [[entité#Type d'entité (Entité)|entité]] $E_1$, $E_2$,...,$E_n$ définit une association entre ces entités. 

L'ensemble des **instance d'une association** est appelé un **ensemble d'association** de $R$

Comme les type d'entité et les ensemble d'entité les type d'association et leur ensemble d'association' sont nommé par $R$

Mathématiquement l'ensemble d'association $R$ est un ensemble **d'instance de association** $r_i$ où chaque $r_i$ associe $n$ entité individuel et donc chaque entité $e_j$ dans $r_i$ est un membre le d'ensemble d'entité $E_j$

Par conséquence l'ensemble d'association et une relation mathématique sur $E_1$,...$E_n$. Il peut aussi être défini comme un sous ensemble du [[produit cartesien]] des ensembles d'entités 

$$E_1 \times E_2 \times...E_n$$
Chaque ensemble d'entité est dit **participant** dans le type d'association $R$ similairement chaque entité individuel $e_n$ est dit **participante** dans l'instance d'association 

$$
r_i = (e_1,...,e_n)
$$
## Degré de relation

Le **degré** d'une relation correspond au nombre d'entité participant a cette relation

## Role

Chaque entité participant à une association joue un **role** particulier. Dans le cas ou chaque entité d'une association est distinct alors il n'est pas nécessaire de lui associé un rôle. 

Cependant il peut arriver qu'une entité apparaisse plus d'une fois dans une relation. On parle alors de [[#Association récursive]]. Dans ce cas-ci il est important de lui associé un rôle

## Association récursive

Une **association récursive** est une association dans laquelle une entité apparaît plusieurs fois mais à des rôles différent

exemple : Soit une entité Employée. Un employé peut aussi être un directeur. Dans ce cas-ci l'entité Employé apparaît deux fois dans la relation $SUPERVISION$

## Cardinalité

La **cardinalité** d'une association défini le nombre maximum d'instance d'association qu'une entité peut participer

exemple : Soit une relation $TRAVAIL$ dans une entreprise qui associé des employé à des département. Cette relation peut avoir une cardinalité $1:N$ signifiant que chaque employé est associé à 1 département. Cela aussi implique que chaque département peut être associé à plusieurs employés

exemple : Dans le cas de association binaire les cardinalité possibles peuvent être :
- `1:N` : Une entité $A$ peut être associé à plusieurs entité $B$ (One-to-many)
- `N:1` : Plusieurs entité $A$ peuvent être associé à une entité $B$ (Many-to-one)
- `1:1` : Une entité $A$ est associé à une entité $B$ (One-to-one)
- `M:N` Plusieurs entité $A$ peuvent être associé à plusieurs entité $B$ (Many-to-many)

## Participation

 La **contrainte de participation** défini le nombre minimum de association auquel une entité doit participé

exemple : Dans une entreprise chaque employé doit forcément être rattaché à un département. Cela implique que chaque instance de l'entité employé doit participé au moins une fois dans une instance de la relation TRAVAIL_POUR. la contrainte de participation de l'entité EMPLOYÉ est donc de 1

### Participation total

Dans l'exemple étant donné qu'un employé doit forcément être rattaché à un département cela implique qu'il ne peut pas exister d'entité EMPLOYÉ sans qu'elle participe à l'association. On parle alors de **participation total**

### Participation partiel

Dans le cas ou une entité n'est pas obligé de participé dans une association on parle alors de **participation partiel** 

exemple : Dans une entreprise un employé pour diriger un département mais pas tout les employé ne dirige un département