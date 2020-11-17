# Configurer la couleur de survol

Suivant la couleur du thème utilisé (et la couleur de la police), le survol des éléments recherchés peut perdre en lisibilité.
La procédure suivante permet de modifier la couleur au survol des éléments :

1. Ouvrir le fichier Catalog/css/style.css
2. Se placer en fin de fichier et sauter une ligne
3. Ajouter les lignes suivantes :
```css
.jimu-widget-catalog .metadata-item:hover
{
background-color: #38a800;
}

.jimu-widget-catalog .free-text {
background-color: transparent;
}
```
4. Enregistrer le fichier
5. Vider le cache et recharger l'application

> Note : Le code couleur (hexadécimal) peut évidemment être remplacé.