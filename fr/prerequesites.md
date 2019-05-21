# Fonctionnement général

Le widget Isogeo fonctionne pour le générateur d'applications web SIG Web AppBuilder for ArcGIS et potentiellement ses dérivés (comme _arcOpole Builder_)

Il [s'ajoute comme tout autre widget aux applications webs](/installation-configuration/installwidget.md) au moment de sa configuration par l'administrateur de la plateforme Portal ou ArcGIS Online. Il est parfaitement intégré à l'interface des applications.

Une fois en place, il permet à l'utilisateur final de [chercher une donnée](/usage/search.md) via une recherche libre, quelques filtres techniques (formats, ressources associées), sémantiques (mots-clés, thèmes INSPIRE, groupes de travail) et géographiques (filtre depuis la carte), des tris (Nom et date de mise à jour de la donnée). 

Il est ensuite possible d’ajouter la donnée via les liens de visualisation documentés (Esri Map, Esri Feature, Esri Tiled Map, WMS en WGS84) et de [consulter la métadonnée](/usage/metadata.md) dans une fenêtre spécifique.

---

# Prérequis

## Isogeo

* au moins un groupe de travail Isogeo dans un abonnement payant ;
* au moins un catalogue contenant au moins une métadonnée de service, partagé à l'application ;
* des clés d'authentification oAuth2 auprès de l'API Isogeo ;

## Environnement technique

* ArcGIS Server 10.3 minimum ;
* Portal for ArcGIS installé et configuré ou un compte ArcGIS OnLine ;
* Application générée avec le WebAppBuilder et déployée sur un serveur Web ;
* Un serveur Web pour le déploiement de l’application avec [PHP](https://secure.php.net/) installé et son extension cURL activée ;
* Au moins un utilisateur nommé Esri ;
* De disposer de services cartographiques publiés sur ArcGIS Server ou sur ArcGIS Online

Le widget est également compatible avec [_arcOpole Builder_](https://www.arcopole.fr/generateur-applications-arcopole-builder.aspx).

