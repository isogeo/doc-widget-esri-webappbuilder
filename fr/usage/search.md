# Rechercher

Le widget de recherche Isogeo s'ouvre au clic sur l'icône catalogue : ![](../../assets/widget_WABDE_icon_color.png) ou automatiquement au chargement de l'application si l'option a été cochée au moment de son ajout (cf. [Ajouter le widget à une application Web AppBuilder](/installation-portal/addwidgetapplication.md)). 

Deux modes de recherche sont proposés :

* standard
* avancé

## Recherche standard {#search_standard}

Par défaut, seul le champ de recherche textuelle et les options de tri (ordre alphabétique des titres et date de mise à jour de la métadonnée) sont affichés.
La recherche textuelle fonctionne de la même manière que pour les autres applications exploitant l'API Isogeo (cf. [La recherche textuelle](https://help.isogeo.com/admin/fr/features/inventory/search.html#la-recherche-textuelle)).

## Recherche avancée {#search_advanced}

En cliquant sur le lien déroulant `Filtres avancés`, des options de recherche supplémentaires s'affichent selon la [configuration du Widget](/installation-portal/addwidgetportal.md):

![](../../assets/widget_WABDE_search_advanced_empty.png "Mode de recherche avancée")

* Filtre par mots-clés : En sélectionnant un mots-clé, la liste n'affiche que des métadonnées contenant ce mots clés.
* Filtre par thématiques du groupe de travail : Idem
* FIltre par thèmes Inspire : Idem
* Filtre par format : Idem
* Filtre sur l'étendue courante de la carte : Seules les données dont les enveloppes convexes sont contenues dans l'emprise de la carte s'affichent.
* Filtre sur la sélection : Utiliser le pinceau pour construire une emprise rectangulaire sur la carte. Cette fois, seules les données dont les enveloppes convexes sont contenues dans l'emprise saisie s'affichent.
* Restreindre aux données visualisables : Afficher uniquement les données ajoutables à la carte.
* Restreindre aux données téléchargeables : Afficher uniquement les données ayant un lien de téléchargement dans la fiche de métadonnée.