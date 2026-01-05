# Contrainte de relation

Il peut exister des contrainte sur les [[relation]] d'une BDD. On distingue 3 catégories :
1. **contrainte implicite** : ce sont les contraintes qui sont inhérent au model de donnée
2. **contraint explicite** : Ce sont les contraintes qui sont défini par l'utilisateur dans le [[DDL]]
3. **règle de gestion** ou **contrainte sémantique** : Ce sont les contrainte qui ne peuvent pas être défini sur le schéma de la BDD et qui doivent être appliqué au niveau de l'application

## Contrainte de domaine

Les contraintes de domaine spécifie sur chaque tuple que la valeur d'un attribut $A$ doit être une valeur atomique du domaine $dom(A)$ 

## Contrainte de clé

Dans le [[model relationnel]] chaque relation est un ensemble de [[relation#Tuple|tuple]]. Par définition chaque élément d'un ensemble est distinct par conséquence chaque tuple doit être distinct. Cela implique qu'il ne peut pas exister deux tuples ayant la même combinaison de valeur pour leur attribut.

Généralement il existe un sous-semble d'attribut d'une relation R avec pour propriété que deux tuple de R ne peuvent avoir les même valeurs.

exemple : Si on appel ce sous ensemble $SK$ alors ont a : 

$$
t_1[SK] \neq t_2[SK]
$$
Cet ensemble $SK$ est appelé la super-clé de la relation $R$. 

Cependant une super-clé peut avoir des attribut redondant on va alors utiliser le concept de **clé**. Une clé possède les propriété suivante :
- Il ne peut exister deux tuples dans une même relation ayant les même valeurs pour clé
- c'est une super-clé minimal. Cela veut dire qu'on ne peut supprimer des attribut appartenant à la super-clé sans brisé la contrainte d'unicité

Si une clé sert à identifier un tuple alors on parle de **clé primaire**. Dans le cas où une clé est juste un attribut unique alors on parle simplement de **clé unique**


