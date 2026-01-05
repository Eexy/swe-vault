# Union

Une **union** permet de représenter un ensemble d'entité provenant de différent [[entité#Type d'entité (Entité)|type d'entité]]. Une union peut aussi être appelé une **catégorie**

Dans le cas d'une union une [[sous-classe & super-classe|sous-classe]] va représenté une collection d'[[entité]] qui est un sous-ensemble de l'union

exemple : Soit 3 entités (PERSONNE, BANQUE, ENTREPRISE) dans une une base de donné concernant l'enregistrement de véhicule. Malgré que ce soit 3 entités distinct chacune de ces entités est une propriétaire de véhicule

![[union example.png]]

Dans cet exemple la sous-classe PERSONNE est une entité qui correspond aussi à un ensemble d'instance d'entité PERSONNE qui fait parti de l'ensemble des PROPRIÉTAIRE. Donc PERSONNE est un sous-ensemble de PROPRIÉTAIRE. PROPIETAIRE est considéré représenté comme une entité

## Représentation graphique

Une union est représenté graphiquement avec un cercle contenant un $u$ reliant la super-classe à ses sous-classe. Un arc de cercle indique le sens de lecture / d'appartenance.