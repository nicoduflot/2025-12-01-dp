# Drupal

## Installation

* Préparer une base de données codage caratère UTFmb4_unicode_ci

* Téléchager les fichier d'installation sur le [site](https://www.drupal.org/project/drupal/releases/)

* Mettre le fichier dans le répertoire de travail
    * dans le fichier.htacess, trouver la ligne suivante : 
    ```batch
    <IfModule mod_php.c>
        php_value assert.active                   0
    </IfModule>
    ```
    Commenter la ligne ```php_value assert.active                   0```
    ```batch
    <IfModule mod_php.c>
    #   php_value assert.active                   0
    </IfModule>
    ```

* Lancer le site via un navigateur
    * Choisir anglais comme langue d'installation
    * Indiquer les informations base de données et utilisateur bases de données
    * Indiquer les informations dont l'utiisateur (admin) principal

## Extensions Indispensables

* Admin toolbar
* token
* pathauto
* chaostools (ctools)

Télécharger les zip et les dézipper dans le répertoire ```modules``` à la racine du site

Ensuite aller dans extends et activer les extensions suivantes
* Multilingual
    1. Language
    2. Interface Translation
    3. Configuration Translation

* Administration
    * Admin toolbar
    * Admin Toolbar Extra Tools
    * Admin Toolbar Search

* other
    * Token
    * Pathauto
* Chaos tool suite
    * Chaos Tools

* Chaos tool suite (Experimental)
    * Chaos Tools Blocks
    * Chaos Tools Views

## Configuration de base

### Changer de langue

#### Ajouter la langue pour l'interface

* Home > Administration > Configuration > Region and language > Languages > Add language
* choisir la langue
* Cliquer sur "Add language"

### Récupérer le fichier de traduction de l'interface

* Home > Administration > Configuration > Region and language > User interface translation
* Cliquer sur "import"
* Cliquer sur le lien ["Drupal translation server"](https://localize.drupal.org/)
* Dans la navigation rapide, ruchercher "Franch" puis le bouton "Go there" ![Navigation rapide](./support/001-fichier-de-trad-fr.png)
* Sur la page suivante, télécharger le fichier correspondant à la version utilisée ![drupal 11](./support/002-fichier-de-trad-fr.png)
* Charger le fichier en demandant de réécrire les traduciton existante ainsi que les traductions faîtes par l'utilisateur ![Configuration de l'import des traductions](./support/003-fichier-de-trad-fr.png)
* Aller à Home > Administration > Configuration > Region and language > Languages 
* Choisir la langue installée comme langue par défaut ![choix de langue et sauvegarde configuration](./support/004-fichier-de-trad-fr.png)

