# Drupal

## Le parcours Drupal

1. [Installation](./001-installation.md)
2. [Extensions Indispensables](./002-extensions-indispensables.md)

## Configuration de base
3. [Changer de langue](./003-changer-de-langue.md)
4. [Utiliser des alias d'url avec Pathauto](./004-alias-d-url.md)
5. [Bibliothèque de media](./005-bibliotheque-media.md)
6. [Formats de saisie](./006-formats-de-saisie.md)

## Préparer les contenus

7. [Création des Taxonomies](./007-creation-des-taxonomies.md)
8. [Ajout d'une taxonomie à un contenu existant](./008-ajoute-taxonomie-contenu.md)
9. [Remplacer le champ image des articles par un champ media type image](./009-remplacer-champ-contenu.md)
10. [Création des taxonomies pour les nouveaux types de contenu](./010-nouvelles-taxonomies.md)
11. [Création d'un type de contenu](./011-creation-nouveau-type-contenu.md)
12. [Les vues](./012-les-vues.md)
13. [Les menus](./013-les-menus.md)
14. [Inclure vues et blocs dans les régions](./014-inclure-les-vues-blocs-dans-la-mise-en-page.md)
15. [Thèmes de base](./015-theme-de-base.md)
16. [Créer un thème enfant](./016-theme-enfant.md)

## Atelier - exercice - td proposé

1. Faire une installation de drupal (sans composer)
2. Activer les extensions présintallées :
    A. Media
    B. Media library
    C. Configuration Translation
    D. Interface Translation
    E. Language
3. Installer activer les extensions suivantes : 
    A. admin toolbar
    B. token
    C. pathauto
    D. chaostools
4. Mettre la langue FR
5. Installer le thème [bootstrap5](https://www.drupal.org/project/bootstrap5/releases/4.0.6)
6. Créer un sous-thème bs5
7. Créer au moins deux types de contenus
8. Créer au moins deux taxonomies
9. Utiliser des champs référence contenu ou taxonomie dans les types de contenus créés
10. Créer au moins une vue regroupant chaque type de contenu (sauf les pages de base) donc trois vues minimum
11. Créer les vues bloc des vues contenus pour les ajouter à l'une des sidebar
12. Gérer ces vues en lien dans le menu

## Migration d'un drupal

Il existe des outils extension qui permettraient la migration d'un site Drupal en local (ou d'un hébergeur) vers un autre hébergeur, mais ces outils ne sont pas très adaptés.

Il est possible cependant de le faire "manuellement" en suivant ses étapes :

* Sauvegarder la base de donnée du site a migrer
    * ATTENTION : dans les données enregistrées, l'adresse utilisée par le site a migrer y apparait environ 300 fois, il faut ouvrir le fichier de saugarde dans un éditeur et remplacer l'adresse actuelle par l'adresse de migration :
        * ancienne adresse : http://www.monsite.local => htt://www.monsite.com
* Sur la base de données du nouvel hébergeur, créer une base de données et y importer la sauvegarde modifiée
* Une fois que la BDD est correctement importée il faut transferrer TOUS les fichiers du site vers l'autre hébergeur
* Il faut renommer le fichier ```\sites\default\settings.php``` par exemple en ```\sites\default\-settings.php```
* Ce fichier de configuration n'est pas modifiable dans son contenu
* En le renommant et en créant un nouveau fichier ```\sites\default\settings.php```, il sera possible d'y copier l'intégralité du fichier renommé.
* il faut modifier le nouveau fichier ```\sites\default\settings.php```, au niveau de la variable ```$databases['default']['default']```, le nom de  la base de données, l'utilisateur ayant les droits de modification de la bdd avec le mot de passe
* Normalement une fois tout cela fait le site devrai s'ouvrir avec la nouvelle adresse

**ATTENTION** 

La migration de la BDD utilisera **TOUS** les comptes créés sur le site en local.
Si le compte principal n'utilise pas un mot de passe complexe, il y a de forts risque de tentative de hack