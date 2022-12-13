# Fonctionnement général

Le widget Isogeo fonctionne pour le générateur d'applications web SIG Web AppBuilder for ArcGIS et potentiellement ses dérivés (comme _arcOpole Builder_)

Il s'ajoute comme tout autre widget aux applications webs au moment de leur configuration par l'administrateur de la plateforme Portal ou ArcGIS Online. Il est parfaitement intégré à l'interface des applications.

Depuis la version 10.6 du Portal, il peut même être intégré directement à celui-ci, ce qui rend possible l'ajout du widget à chaque création d'une application Web AppBuilder dans Portal.

Une fois en place, il permet à l'utilisateur final de [chercher une donnée](/usage/search.md) via une recherche libre, quelques filtres techniques (formats, ressources associées), sémantiques (mots-clés, thèmes INSPIRE, groupes de travail) et géographiques (filtre depuis la carte), des tris (Nom et date de mise à jour de la donnée). 

Il est ensuite possible d’ajouter la donnée via les liens de visualisation documentés (Esri Map, Esri Feature, Esri Tiled Map, WMS en WGS84) et de [consulter la métadonnée](/usage/metadata.md) dans une fenêtre spécifique.

---

## Prérequis {#prerequesites}

### Isogeo {#isogeo}

* au moins un groupe de travail Isogeo ;
* au moins un catalogue contenant au moins une métadonnée de service, partagé à l'application ;
* des clés d'authentification oAuth2 auprès de l'API Isogeo ;

### Serveur {#server}

* Serveur Web configuré (Apache, IIS...)
* Certificat SSL valide
  
### Réseau {#network}

#### Liste blanche API Isogeo {#cross-domain-list}

L'URL de votre serveur Web doit être ajoutée à la liste blanche des URLS autorisées à contacter l'API Isogeo. 
Par exemple, pour le [Widget de demo](https://carto.isogeo.net/widget_isogeo_webappbuilder_demo), nous avons autorisé les appels de https://carto.isogeo.net
Il faut donc nous fournir cette url en amont de l'installation. 

#### Navigateur client {#client}

Les URL(s) suivantes doivent être accessibles sur le navigateur de l'utilisateur :

* https://id.api.isogeo.com/*
* https://v1.api.isogeo.com/*

Pour tester la communication, ouvrez les url(s) suivantes :

* https://v1.api.isogeo.com/about
* https://id.api.isogeo.com/about  

 Dans les deux cas, la version de l'API devrait s'afficher en JSON.

### Logiciels {#softwares}

* ArcGIS Server > 10.6
* Portal for ArcGIS > 10.6
* Application générée avec le Web AppBuilder dans Portal ou déployée sur un serveur Web
* Utilisateur nommé Esri administrateur du Portal ou ayant les droits de création d'une extension d'application Web AppBuilder (nécéssaire pour l'installation)
* Services cartographiques publiés sur ArcGIS Server et recensés dans Isogeo (internes ou plublics)

### Arcopole Builder {#arcopole}

Le widget est également compatible avec [_arcOpole Builder_](https://www.arcopole.fr/generateur-applications-arcopole-builder.aspx). Vous pouvez suivre la [documentation officielle](https://www.arcopole.fr/aide/builder/v1.4/guides/utilisation/#!avance/AjouterWidgetTier/AjouterWidgetTier.md) pour ajouter le Widget à Arcopole.