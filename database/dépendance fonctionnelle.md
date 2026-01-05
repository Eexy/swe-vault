# Dépendance fonctionnelle

Une **dépendance fonctionnelle** est une contrainte entre deux ensemble d'[[relation#Attribut|attributs]] $X$ et $Y$ d'une [[relation]] $R$ que l'on écrit $X \rightarrow Y$. La contrainte est que pour toute paire de tuple $t_1$ et $t_2$ on $t_1[X] = t_2[X]$ alors ont a $t_1[Y]=t_2[Y]$

En d'autre terme cela indique que l'on peut déterminer la valeurs des attribut $Y$ en connaissant la valeur des attribut $X$

Exemple : Soit une relation PERSONNE qui est égale à 

$$PERSONNE = \{ NOM, PRENOM, NUMERO\_SECURITE\_SOCIALE\}$$

Etant donné que le numéro de sécurité sociale est unique à chaque personne alors juste en ayant sa valeur je peut determiner la valeur des autre attributs

Dans le cas d'une dépendance fonctionnelle l'ensemble d'attribut $X$ est appelé le **coté gauche** et $Y$ le **coté droit**

## Dépendance fonctionnelle complète

On parle de **dépendance fonctionnelle complète** si tous les attribut de $X$ sont nécessaire pour déterminer $Y$. 

## Dépendance fonctionnelle partielle

On parle de **dépendance fonctionnelle partielle** si lorsqu'on retire un attribut de $X$ ont peut encore déterminer $Y$ 

## Transitivité fonctionnelle

La **transitivité fonctionnelle** est une dépendance fonctionnelle $X \rightarrow Y$ si on à un ensemble d'attribut $Z$ tel qu'on a 

$$
X \rightarrow Z \rightarrow Y
$$
Avec pour condition que $Z$ n'est pas la [[attribut#Clé|clé]] et n'est ni un sous-ensemble de la clé

