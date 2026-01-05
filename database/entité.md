
# Entité

**Entité** : L'entité est une chose ou un objet du monde réel qui est indépendante

## Type d'entité (Entité)

un **type d'entité** (fait référence à l'entité de manière générale) définit un ensemble d'entités possédant les même attributs mais ayant des valeurs différentes

exemple : une BDD d'entreprises peut avoir plusieurs entités employé. Chaque employé possède les mêmes attributs mais avec des valeurs différentes

## Ensemble d'entité

La collection de toute de toute les instance d'entités d'un [[#Type d'entité]] dans une BDD à n'importe quel moment est appelé un **ensemble d'entité** 

Lorsqu'on réfère à un ensemble d'entité on utilise en général le nom de l'entité

## Entité faible

Une **entité faible** est une entité est une entité ne possédant pas de clé. Les entité faible sont identifié via l'association à d'autre entité. Ces autres entité sont alors les **propriétaire**.  L'association liant une entité faible à une entité normal est appelé une **association identifiante**.

Une entité faible est toujours dans une participation total dans cette association. La clé qui permet de relié l'entité faible à son propriétaire est appelé une **clé partiel**
