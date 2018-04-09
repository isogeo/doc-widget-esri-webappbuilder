# Configuration du proxy

Installer un proxy sur son serveur Web \(choisir parmi PHP, .NET ou Java\) à partir de ceux mis à disposition par Esri : [https://github.com/esri/resource-proxy/releases](https://github.com/esri/resource-proxy/releases).

Configurer le proxy dans le fichier config.json principal en y ajoutant la règle suivante :

```json
{
    "urlPrefix": "https://api.isogeo.com",
    "proxyUrl": http://mon-serveur/proxy/proxy.php
}
```

> Plus d’information sur le proxy : [http://doc.arcgis.com/en/web-appbuilder/manage-apps/use-proxy.htm](http://doc.arcgis.com/en/web-appbuilder/manage-apps/use-proxy.htm)

## Configurer l'authentification à l'API Isogeo

A l'instar de toutes les applications tierces Isogeo, le widget doit s'authentifier à la plateforme. C'est ce mécanisme qui permet de sécuriser les échanges et de permettre aux administrateurs de configurer à quels catalogues un widget a accès :

1. Editer le fichier `proxy/proxy_isogeo.php` 
2. Remplacer les valeurs `$auth_id` et `$auth_secret` par les valeurs transmises par l'équipe Isogeo :

```php
$auth_id = 'widget-esri-webappbuilder-organisme-uuid-super-unique';
$auth_secret = 'dont-look-i-m-secret';
```



