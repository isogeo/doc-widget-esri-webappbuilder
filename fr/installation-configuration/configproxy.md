# Configuration du proxy


Installer un proxy sur son serveur Web (choisir parmi PHP, .NET ou Java) à partir de ceux mis à disposition par Esri : https://github.com/esri/resource-proxy/releases.

Configurer le proxy dans le fichier config.json principal en y ajoutant la règle suivante :

```json
{
    "urlPrefix": "https://api.isogeo.com",
    "proxyUrl": http://mon-serveur/proxy/proxy.php
}
```

> Plus d’information sur le proxy : http://doc.arcgis.com/en/web-appbuilder/manage-apps/use-proxy.htm