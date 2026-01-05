# Algèbre relationelle

L'algèbre relationnelle permet de manipuler des [[relation]] et de venir en créer de nouvelle.

L’algèbre relationnelle est important pour 3 raisons : 
1. C'est une fondation formelle du [[model relationnel]]
2. Permet implémenté et d'optimiser les queries
3. C'est concepts sont implémentés dans le standard [[SQL]]

## Opérations

L'algèbre relationnelle possède différents opérations. Certaines sont hérité de la théories des ensembles et d'autres qui ont été spécialement

### SELECT

L'opération `select`  permet de choisir un sous-ensemble de tuples d'une relation basé sur une condition.

On l'écrit de la manière suivante :

$$
\sigma<condition>(R)
$$

Le résultat d'un select possède les même [[attribut]] que la [[relation]] $R$

La condition d'un select suit les formes suivante :

1. utilisation d'une constante

$$
<nom de l'attribut><operateur><constant>
$$
2. utilisation d'un attribut

$$
<attribut><operateur><attribut>
$$

On peut aussi assemblé plusieurs conditions par 

1. disjonction : ou

$$
<attribut1><operateur><constant1> \ OR \ <attribut2><operateur><constant2>
$$

2. conjonction : et

$$
<attribut1><operateur><constant1> \ AND \ <attribut2><operateur><constant2>
$$

### PROJECTION

L'opération `project` permet de sélectionner certaines colonnes d'une relation. Cela permet de sélectionner seulement les [[attribut]] qui nous intéresse.

On l'écris de la manière suivant

$$
\pi <attribut>(R)
$$

On peut voir la projection comme une séparation vertical. C'est à dire que l'on sépare la [[relation]] en deux relations. Une relation ayant les colonnes (attribut) voulu et une relation contenant le reste

Dans le cas d'une projection il n'existe pas de tuple en doublon cela revient à faire un `DISTINCT`

### Ordre des opération et renommage

Les expression relationnelle peuvent soit être représenté en tant qu’opération imbriqué ou on peut les représenté en tant que suite d'operation en créant des résultat intermédiaire

1. operation imbriqué 
$$
\pi<attribut>(\sigma<condition(R)>)
$$

2. Suite opérations

$$
RESULT\_TEMP \leftarrow \sigma<condition>(R) 
$$
$$
RESULTAT \leftarrow \pi<attribut>(RESULTAT\_TEMP)
$$

On peut aussi renommé les attributs en associant une projection à un nouveau resultat

$$
R(<nouveau \ attributs> \leftarrow \pi<attribut>(R))
$$

### Renommage

Cette operation permet de renommer des [[attribut]] ou une [[relation]]. Elle s'écrit de la manière suivante

$$
\rho_s(B_n)
$$

avec :
- $S$ : le nouveau nom de la relation
- $B_n$ : le nouveau nom des attributs


### Opération hérité des ensemble

Etant donné que l'on travaille avec des ensemble de tuples on hérite aussi des opérations venant de la théorise des ensembles.

Cependant ces opérations ne peuvent être appliqués seulement sur des [[relation]] **compatible**. Deux relations sont dites compatibles si et seulement si elles ont le même [[relation#Degré|degré]] et si le [[relation#Domaine|domaine]] de leur attribut est le même

Chacune de ses opérations ne contient aucun doublons

#### Union

L'union noté $R \cup U$ est une relation contenant tout les tuples de la relation $R$ et $U$

#### Intersection

L'intersection noté $R \cap U$ est une relation contenant tout les tuples qui sont à la fois dans $R$ et dans $U$

#### Difference

La différence noté $R - U$  est une relations qui inclus tous les tuples de $R$ mais qui ne sont pas dans $U$

#### Produit cartésiens

Le produit cartésiens est la seule opérations n'ayant pas besoin de travaillé avec des relations compatibles

On la note $R \times U$. Cette opérations résulte en une nouvelle relations dont pour chaque tuple de $R$ il existe une combinaisons avec tous les tuples de $U$

En [[SQL]] le produit cartésiens est représenté avec le `CROSS  JOIN`

Le nombre de tuple d'un produit cartésiens est égale a :

$$
n_R * n_U
$$
où :
- $n_R$ : correspond au nombre de tuple contenu dans $R$
- $n_U$ : correspond au nombre de tuple contenu dans $U$

### JOIN

L'opération `JOIN` permet de combiner des tuples associé provenant de deux [[relations]] créant de nouveau tuple.

Elle est écrite de la façon suivante :

$$
R_1 \bowtie<condition> R2
$$

On a : 
- $R1$ : premiere relation
- $condition$ : condition jointure
- $R2$ : seconde relation

La jointure peut âtre aussi représenté comme un [[#Produit cartésiens]] suivi d'un [[#SELECT]]

Le résultat d'une jointure nous donne un ensemble de tuples composé de $n +m$ attributs avec d'abord les tuples de $R1$ puis les tuples de $R2$.

Il est important de noter que seulement les tuples de $R1$ qui peuvent se combiné avec les tuples de $R2$ sont préservés

Enfin le nombre de tuples d'une jointure est comprise entre $0$ et $n_R1 * n_R2$

## Query tree

Un **query tree** est un arbre permettant de représenter comment les opérations sont évaluées. Cela reprend la même forme que les [[arbre d'expression]]

Dans un query tree chaque feuille correspond à une relation et chaque nœud correspond à une relation

![[query tress.png]]