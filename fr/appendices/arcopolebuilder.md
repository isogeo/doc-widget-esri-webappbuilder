# Intégrer le Widget à Arcopole Builder

Le widget est également compatible avec [_arcOpole Builder_](https://www.arcopole.fr/generateur-applications-arcopole-builder.aspx). 

Cependant, il ne peut pas être hébergé par Isogeo et appelé dans l'application comme pour le Portail Esri. 

Il faut donc déposer le code du Widget dans le répertoire des plugins prévu par Arcopole [cf. documentation officielle](https://www.arcopole.fr/aide/builder/v1.4/guides/utilisation/#!avance/AjouterWidgetTier/AjouterWidgetTier.md) puis configurer le fichier `config.json` pour appeler le bon partage de données.

Par exemple, pour notre Widget de démo dont l'url générée dans App est la suivante https://widget-wab.isogeo.com/8d491301f61249139918e3710cd39eb7/wak8OBU2hQX6F6rtIe3fWiRCvzFH0/manifest.json, cela donne : 

```json
"apiUrl":https://isogeo-widget-esri-webappbuilder.azurewebsites.net/api,
"useUrlSecrets":false,
"share":"8d491301f61249139918e3710cd39eb7",
"token":"wak8OBU2hQX6F6rtIe3fWiRCvzFH0",
```    

De ce fait, les mises à jour ne peuvent être automatisées. Il faut donc remplacer le code source du Widget à chaque nouvelle version et veiller à conserver les paramètres du fichier `config.json`. 