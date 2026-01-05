# Dépendances multivaluées

Une **dépendances multivaluées** est une [[dépendance fonctionnelle]] que l'on écrit right $X \twoheadrightarrow Y$  dans laquelle  [[relation#Attribut|l'attribut]] $X$ détermine un ensemble de valeurs possible pour l'attribut $Y$


La définition mathématique est la suivante : 

Soit une relation R avec pour ensemble d'attributs X, Y et Z avec Z qui est égale à $R - (X \cup Y)$ (autrement dit l'ensemble d'attribut qui ne sont ni dans $X$ et ni dans $Y$)

On a une dépendances multivaluées s'il existe 4 tuples $t_1$, $t_2$, $t_3$ et $t_4$ (les tuples ne sont pas obligé d'être distinct donc $t_3 = t_2$ par exemple) et que l'on a 

$$
t_3[X] = t_4[X] = t_2[X] = t_1[x]
$$
$$
t_3[Y]=t_1[Y] \ et \ t_2[Y]=t_4[Y]
$$
$$
t_3[Z]=t_2[Z] \ et \ t_1[Z]=t_4[Z]
$$

On remarque par cette définition que $t_1$ et $t_3$ possèdent le même ensemble de valeurs pour l'ensemble d'attribut $Y$ mais que cet ensemble de valeurs et différent pour les tuples $t_2$ et $t_4$ alors qu'ils partagent tous le même ensemble de valeurs de $X$ et cela indépendamment de la valeurs de $Z$

exemple : Soit une relation $COURS(etudiant, cours,textbook)$ qui répertorie l'ensembles des cours d'un étudiant on peut avoir 

| étudiant | cours | textbook      |
| -------- | ----- | ------------- |
| John     | Math  | algèbre       |
| John     | CS    | programmation |
| Jhon     | Math  | statistique   |
| John     | CS    | Algorithme    |

On remarque que pour John on à différentes valeurs possibles pour les cours possibles et cela indépendamment de la valeurs de textbook

### Dépendance multivaluées trivial / non trivial

Une dépendance multivaluées est dite **trivial** si elle l'ensemble d'attribut $Y$ est un sous-ensemble de $X$ ou si l'union de $X$ et de $Y$ correspond à l'ensemble des attribut de $R$ 

Si elle ne respecte pas l'une de ces deux règles alors elle est dite **non trivial**