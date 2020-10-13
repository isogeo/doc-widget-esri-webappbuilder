# Installation du Widget Isogeo

## Configurer l'authentification à l'API Isogeo

A l'instar de toutes les applications tierces Isogeo, le widget doit s'authentifier à la plateforme. C'est ce mécanisme qui permet de sécuriser les échanges et de permettre aux administrateurs de configurer à quels catalogues un widget a accès :

1. Dezipper l'archive contenant le code du widget ;
2. Editer le fichier `proxy/proxy_isogeo.php` ;
3. Remplacer les valeurs `$auth_id` et `$auth_secret` par les valeurs transmises par l'équipe Isogeo ;

```php
//Configuration
$auth_id = 'widget-esri-webappbuilder-organisme-uuid-super-unique';
$auth_secret = 'dont-look-i-m-secret';
```

## Installation du proxy Isogeo

Copier le fichier `proxy_isogeo.php` sur le serveur Web. Selon le serveur web, le répertoire par défaut est le suivant :

* Linux : `/var/www/html/`
* Windows Apache : `C:\Applications\Apache24\htdocs`
* Windows IIS : `C:\inetpub\wwwroot\`

## Installation du Widget

Copier le répertoire `catalog` sur le serveur Web et récupérer son URL (note, la configuration sera plus simple si l’URL est sur le même domaine que Portal)

Editer le fichier `catalog/config.json` et paramétrer l’URL du proxy Isogeo :

```json
{
    "proxyUrl": https://mon-serveur/proxy_isogeo.php
}
```

Vous pouvez également modifier les paramètres suivants :

* resultSymbol : Symbole de type polygone au format ESRI Json
* resultSymbolPoint: Symbole de type point (donneés ne contenant pas d’emprise) au format ESRI Json
* popupWidth : largeur de la popup pour les métadonnées (400 pour les autres couches)
* popupMoveLeft : Décalage de la popup (pour les modèles d’applications nécessitant un décalage)
* wfsMode : "snapshot" (requête initiale uniquement) ou "ondemand" (requête à chaque déplacement, mais non
compatible avec tout les flux WFS)
* wfsMaxFeatures : Nombre maximal d’entités récupérées dans un flux wfs
* relationGeo : Relation géographique pour les recherche par emprise
* datasetOnly": Afficher uniquement les données rasters et vecteurs (pas de fiches de services ou de fiches ressources)
* tabLayers": Afficher l'onglet Couches
* tabContexts": Afficher l'onglet Contexte