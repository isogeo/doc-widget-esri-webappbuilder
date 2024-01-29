# Fonctionnement général

Le widget Isogeo fonctionne pour le générateur d'applications web SIG Web AppBuilder for ArcGIS et potentiellement ses dérivés (comme _arcOpole Builder_)

Il s'ajoute comme tout autre widget aux applications webs au moment de leur configuration par l'administrateur de la plateforme Portal ou ArcGIS Online. Il est parfaitement intégré à l'interface des applications.

Depuis la version 10.6 du Portal, il peut même être intégré directement à celui-ci, ce qui rend possible l'ajout du widget à chaque création d'une application Web AppBuilder dans Portal.

Une fois en place, il permet à l'utilisateur final de [chercher une donnée](/usage/search.md) via une recherche libre, quelques filtres techniques (formats, ressources associées), sémantiques (mots-clés, thèmes INSPIRE, groupes de travail) et géographiques (filtre depuis la carte), des tris (Nom et date de mise à jour de la donnée). 

Il est ensuite possible d’ajouter la donnée via les liens de visualisation documentés (Esri Map, Esri Feature, Esri Tiled Map, WMS en WGS84) et de [consulter la métadonnée](/usage/metadata.md) dans une fenêtre spécifique.

---

## Prérequis {#prerequesites}

Le Widget étant hébergé par Isogeo, aucune installation sur un serveur Web n'est nécessaire pour son fonctionnement. 

### Isogeo {#isogeo}

* au moins un groupe de travail Isogeo ;
* au moins un catalogue contenant au moins une métadonnée de service, partagé à l'application Web AppBuilder;

### Logiciels {#softwares}

* ArcGIS Server > 10.6
* Portal for ArcGIS > 10.6
* Application générée avec le Web AppBuilder dans Portal
* Utilisateur nommé Esri administrateur du Portal ou ayant les droits de création d'une extension d'application Web AppBuilder (nécessaire pour le référencement dans Portal)
* Services cartographiques publiés sur ArcGIS Server et recensés dans Isogeo (privés ou publics)

> NB : En mode On-premises, pour pouvoir référencer le widget Web AppBuilder dans Portal for ArcGIS, il est nécéssaire que le certificat racine utilisé par la solution Isogeo soit approuvé par celui-ci (cf. [documentation officielle d'Esri](https://enterprise.arcgis.com/fr/portal/latest/administer/windows/configuring-the-portal-to-trust-certificates-from-your-certifying-authority.htm)).

### Réseau {#network}

* Accès à https://widget-wab.isogeo.com/manifest.json pour le compte qui lance le service Windows Portal (ou à travers le proxy système)

Si l'accès n'est pas autorisable, il est possible de déployer le Widget directement sur le serveur Web du Portal (Apache, IIS).

### Arcopole Builder {#arcopole}

Le widget est également compatible avec [_arcOpole Builder_](https://www.arcopole.fr/content/aob) (cf. [Intégrer le Widget à Arcopole](../appendices/arcopolebuilder.md))