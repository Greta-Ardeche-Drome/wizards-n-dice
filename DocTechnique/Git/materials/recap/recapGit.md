# Récapitulatif - Git et SourceGit

## Sommaire

## Introduction
Cette fiche récapitulative a pour but de présenter l'essentiel des opérations que l'on sera amenés à faire durant le PTUT. Elles seront présentées avec l'outil GUI SourceGit, couplées à leur équivalent avec l'outil CLI.

Je conseille de travailler avec l'interface de SourceGit en anglais, car certains termes francisés des différents process Git rendent les choses plus complexes à retenir. De plus, si vous voulez aller chercher de la documentation sur le sujet, vous la trouverez le plus souvent en anglais. (comme tout...)

## Première mise en place
### Cloner le repo
Pour cloner le repo, je conseille d’utiliser l’outil CLI de git ; cela peut éviter les soucis étant donné que l’on clone avec une adresse SSH.

Pour cloner le repo, taper ceci : 
```bash
git clone git@github.com:Greta-Ardeche-Drome/wizards-n-dices.git
```

### Configurer le repo
Configurer le repo cloné veut dire ici la spécification de l’utilisateur et de l’adresse e-mail poussés avec un commit.
```bash
git config user.name "Prénom NOM"
git config user.email "adresse@mail.org"
```

## Suivi des fichiers
### Ajouter un fichier au suivi
#### Dans SourceGit
Cliquer sur "Changes", vous basculez dans une nouvelle fenêtre où vous voyez la liste des changements.
![alt text](image.png)

On ajoute les changements que l'on veut à l'index en cliquant dessus ou en cliquant sur l'icône mise en évidence ci-dessous, ce qui ajoute tous les changements non indexés à l'index. En anglais, l'index s'appelle le "stage".
![alt text](image-1.png)

Rappelez-vous qu'on ne peut pas ajouter un dossier vide à l'index, il est obligatoire de créer un fichier dans le dossier en question pour qu'il apparaisse dans le repo distant.

#### Avec l'outil CLI
Ajouter un certain fichier au suivi :
```bash
git add chemin/vers/le/fichier
```

Ajouter tous les changements non indexés à l'index :
```bash
git add .
```

### Créer un commit
#### Dans SourceGit
Une fois les changements indexés, on crée un commit pour sauvegarder leur état dans l'historique du repo. Dans la fenêtre "Changes", il y a un espace pour créer un message de commit avec titre et description. La description n'est pas obligatoire.
![alt text](image-2.png)

Une fois le message écrit, il suffit de cliquer sur "Commit".