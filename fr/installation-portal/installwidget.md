# Installation et configuration du Widget Isogeo

1. Dezipper l'archive contenant le code du widget ;
2. Copier le répertoire `catalog` sur le serveur Web et récupérer son URL d'accès
   1. Linux : `/var/www/html/`
   2. Windows Apache : `C:\Applications\Apache24\htdocs`
   3. Windows IIS : `C:\inetpub\wwwroot\`
3. Editer le fichier `catalog/config.json` et indiquer les paramètres d'authentification à l'API Isogeo :

```json
{
    "client_id":"widget-esri-webappbuilder-XXXXXXX",
    "client_secret":"xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
}
```
## Filtrer les résultats sur des données en particuliers {#share-dataset-only}

Si vous souhaitez limiter les résultats à un partage de données (interne VS grand public par exemple), vous pouvez indiquer l'identifiant du partage dans le paramètre `share` du fichier de configuration.

Par exemple, pour le partage de démonstration, nous récupérons l'identifiant dans l'url du partage sur la plateforme d'administration (en gras ci-dessous). 

https://app.isogeo.com/groups/8e02046c031a454690efe71692d25db5/admin/shares/**1b440817e62c45c19ae206e6e260ace9** 

Si vous souhaitez également n'afficher que les fiches sur les données rasters, vecteurs et tabulaires non géographiques et masquer les fiches de services, vous pouvez compléter le paramètre `dataset-only` à `true`. 

```json
{
    "share":"1b440817e62c45c19ae206e6e260ace9",
    "dataset-only": true,
}
```
## Autres configurations possibles

Vous pouvez également modifier les paramètres suivants :

* link : lien vers la page de présentation du Widget sur le site officiel d'Isogeo
* resultSymbol : Symbole de type polygone au format ESRI Json
* resultSymbolPoint: Symbole de type point (donneés ne contenant pas d’emprise) au format ESRI Json
* popupWidth : largeur de la popup pour les métadonnées (400 pour les autres couches)
* popupMoveLeft : Décalage de la popup (pour les modèles d’applications nécessitant un décalage)
* wfsMode : "snapshot" (requête initiale uniquement) ou "ondemand" (requête à chaque déplacement, mais non
compatible avec tout les flux WFS)
* wfsMaxFeatures : Nombre maximal d’entités récupérées dans un flux wfs (1000 par défaut)
* relationGeo : Relation géographique pour les recherches par emprise
* tabLayers : Afficher l'onglet Couches
* tabContexts : Afficher l'onglet Contexte
* openFiltersAtStart : Déplier tous les filtres à l'ouverture du Widget
* filterKeyword : Afficher le filtre sur les mots-clés
* filterOwner : Afficher le filtre sur le propriétaire
* filterThematic : Afficher le filtre sur les thématiques
* filterTheme : Afficher le filtre sur les thèmes Inspire
* filterFormat : Afficher le filtre sur les formats
* filterGeo : Afficher le filtre sur l'étendue de la carte
* filterSelection : Afficher le filtre sur une zone dessinée
* filterView : Afficher le filtre sur les données visualisables
* filterDownload : Afficher le filtre sur les données téléchargeables
* footer : Afficher le pied de page
* useMetadataName : Afficher le nom de la métadonnée comme nom du service/de la couche (dans les widgets *Legende* et *Liste des couches*) ou le nom ArcGIS Server par défaut.
* filterDomain : Afficher le filtre sur les domaines
* domains : Indiquer la liste des [thématiques](https://help.isogeo.com/admin/fr/features/admin/group_themes.html) que vous souhaitez afficher dans le filtre *Domaines* (s'il est activé) et non dans le filtre *Thématiques*. Indiquer les termes entre guillements et les séparer par des virgules.


> NB : Pour information, le portail chargera automatiquement la configuration saisie dans le fichier `catalog/config.json` à chaque ajout du widget dans une nouvelle application Web AppBuilder. Dans une application existante, il faut vérifier que l'utilisateur n'a pas modifié la configuration directement depuis le Portal (cf. [Ajouter le widget à une application Web AppBuilder](/installation-portal/addwidgetapplication.md))
