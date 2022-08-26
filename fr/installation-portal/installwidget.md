# Installation du Widget Isogeo

## Configurer l'authentification à l'API Isogeo

A l'instar de toutes les applications tierces Isogeo, le widget doit s'authentifier à la plateforme. C'est ce mécanisme qui permet de sécuriser les échanges et de permettre aux administrateurs de configurer à quel(s) catalogue(s) un widget a accès :

1. Dezipper l'archive contenant le code du widget ;
2. Editer le fichier `proxy/proxy_isogeo.php` ;
3. Remplacer les valeurs `$auth_id` et `$auth_secret` par les valeurs transmises par l'équipe Isogeo ;

```php
$auth_id = 'widget-esri-webappbuilder-organisme-uuid-super-unique';
$auth_secret = 'dont-look-i-m-secret';
```
En cas d'utilisation d'un serveur proxy pour l'accès à Internet, il faut indiquer les paramètres d'authentification à celui-ci selon le modèle ci-dessous :

```php
$proxy = '127.0.0.1:8080';
$proxyauth = 'domaine\user:pass';
```
Au besoin, vous pouvez également activer le cross-domain en autorisant les appels d'un domaine spécifique ou de tous les domaines :

```php
header("Access-Control-Allow-Origin: https://host.domain.com");
header("Access-Control-Allow-Origin: *");
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
* openFiltersAtStart": Déplier tous les filtres à l'ouverture du Widget
* filterKeyword": Afficher le filtre sur les mots-clés
* filterOwner": Afficher le filtre sur le propriétaire
* filterThematic": Afficher le filtre sur les thématiques
* filterTheme": Afficher le filtre sur les thèmes Inspire
* filterFormat": Afficher le filtre sur les formats
* filterGeo": Afficher le filtre sur l'étendue de la carte
* filterSelection": Afficher le filtre sur une zone dessinée
* filterView": Afficher le filtre sur les données visualisables
* filterDownload": Afficher le filtre sur les données téléchargeable
* footer": Afficher le pied de page

> NB : Pour information, le portail chargera automatiquement la configuration saisie dans le fichier `catalog/config.json` à chaque ajout du widget dans une nouvelle application Web AppBuilder. Dans une application existante, il faut vérifier que l'utilisateur n'a pas modifié la configuration directement depuis le Portal (cf. [Ajouter le widget à une application Web AppBuilder](/installation-portal/addwidgetapplication.md))
<!-- * useMetadataName": -->