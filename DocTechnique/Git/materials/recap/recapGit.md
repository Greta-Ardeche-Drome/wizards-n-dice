# Récapitulatif - Git et SourceGit

## Sommaire
- [Récapitulatif - Git et SourceGit](#récapitulatif---git-et-sourcegit)
  - [Sommaire](#sommaire)
  - [Introduction](#introduction)
  - [Première mise en place](#première-mise-en-place)
    - [Cloner le repo](#cloner-le-repo)
    - [Configurer le repo](#configurer-le-repo)
  - [Suivi des fichiers](#suivi-des-fichiers)
    - [Ajouter un fichier au suivi](#ajouter-un-fichier-au-suivi)
      - [Dans SourceGit](#dans-sourcegit)
      - [Avec l'outil CLI](#avec-loutil-cli)
    - [Créer un commit](#créer-un-commit)
      - [Dans SourceGit](#dans-sourcegit-1)
      - [Avec l'outil CLI](#avec-loutil-cli-1)
    - [Supprimer un fichier suivi par Git en le conservant localement](#supprimer-un-fichier-suivi-par-git-en-le-conservant-localement)
      - [Dans SourceGit](#dans-sourcegit-2)
      - [Avec l'outil CLI](#avec-loutil-cli-2)
  - [Travailler avec l'historique](#travailler-avec-lhistorique)
    - [Visualiser l'historique](#visualiser-lhistorique)
      - [Dans SourceGit](#dans-sourcegit-3)
      - [Avec l'outil CLI](#avec-loutil-cli-3)
    - [Afficher les détails d'un commit spécifique](#afficher-les-détails-dun-commit-spécifique)
      - [Dans SourceGit](#dans-sourcegit-4)
      - [Avec l'outil CLI :](#avec-loutil-cli-)
  - [Branches](#branches)
    - [Créer une nouvelle branche](#créer-une-nouvelle-branche)
      - [Dans SourceGit](#dans-sourcegit-5)
      - [Avec l'outil CLI](#avec-loutil-cli-4)
    - [Changer de branche active](#changer-de-branche-active)
      - [Dans SourceGit](#dans-sourcegit-6)
      - [Avec l'outil CLI](#avec-loutil-cli-5)
    - [Fusionner une branche souhaitée dans la branche active](#fusionner-une-branche-souhaitée-dans-la-branche-active)
      - [Dans SourceGit](#dans-sourcegit-7)
      - [Avec l'outil CLI](#avec-loutil-cli-6)
    - [Lister les branches](#lister-les-branches)
      - [Dans SourceGit](#dans-sourcegit-8)
      - [Avec l'outil CLI](#avec-loutil-cli-7)
    - [Récupérer un commit spécifique d'une autre branche et le copier sur la branche active](#récupérer-un-commit-spécifique-dune-autre-branche-et-le-copier-sur-la-branche-active)
      - [Dans SourceGit](#dans-sourcegit-9)
      - [Avec l'outil CLI](#avec-loutil-cli-8)
    - [Résoudre des conflits de fusion post-merge ou pull](#résoudre-des-conflits-de-fusion-post-merge-ou-pull)
      - [Dans SourceGit](#dans-sourcegit-10)
      - [Avec l'outil CLI](#avec-loutil-cli-9)
  - [Travailler avec un repo distant](#travailler-avec-un-repo-distant)
    - [Tirer les changements du repo distant (pull)](#tirer-les-changements-du-repo-distant-pull)
      - [Dans SourceGit](#dans-sourcegit-11)
      - [Avec l'outil CLI](#avec-loutil-cli-10)
    - [Récupérer l'historique des commits de toutes les branches sans les télécharger (fetch)](#récupérer-lhistorique-des-commits-de-toutes-les-branches-sans-les-télécharger-fetch)
      - [Dans SourceGit](#dans-sourcegit-12)
      - [Avec l'outil CLI](#avec-loutil-cli-11)
    - [Pousser les changements sur le repo distant (push)](#pousser-les-changements-sur-le-repo-distant-push)
      - [Dans SourceGit](#dans-sourcegit-13)
      - [Avec l'outil CLI](#avec-loutil-cli-12)
  - [Workflow général](#workflow-général)
  - [Bonnes pratiques](#bonnes-pratiques)


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

Une fois le message écrit, il suffit de cliquer sur "Commit". En revenant dans la fenêtre "Histories", le commit apparaît dans l'historique.
![alt text](image-3.png)

#### Avec l'outil CLI
```bash
git commit -m "message de commit"
```

### Supprimer un fichier suivi par Git en le conservant localement
#### Dans SourceGit

#### Avec l'outil CLI

## Travailler avec l'historique
### Visualiser l'historique
#### Dans SourceGit
L'interface de SourceGit, et de n'importe quel autre outil GUI d'ailleurs, a comme fenêtre principale l'historique en "graph" et synthétise les infos de chaque commit en une ligne.

#### Avec l'outil CLI
Affichage classique :
```bash
git log
```

Affichage plus compact :
```bash
git log --oneline
```

Affichage en "graph" :
```bash
git log --graph
```

Affichage en "graph" plus compact (plus proche de l'interface SourceGit) :
```bash
git log --graph --oneline
```

Exemple :
![alt text](image-4.png)

### Afficher les détails d'un commit spécifique
#### Dans SourceGit
Cliquer sur un commit permet de voir plusieurs informations, séparées en trois onglets : les infos générales et les changements.
![alt text](image-5.png)

Les infos générales regroupent la plupart des infos que l'on souhaite récupérer d'un coup d'œil, à savoir :
- les infos sur l'auteur du commit,
- les branches sur lesquelles est le commit,
- le message de commit,
- les changements des fichiers liés au commit.

#### Avec l'outil CLI :
Une commande, parmi d'autres, d'obtenir des infos sur un commit en particulier, est la suivante :
```bash
git show <commit-id>
```
où le `<commit-id>` correspond au hash du commit visé.

## Branches
### Créer une nouvelle branche
#### Dans SourceGit
Cliquer sur un commit pour l'avoir en surbrillance dans l'historique, cliquer sur l'icône mise en évidence :
![alt text](image-6.png)

**ATTENTION :** Committez vos changements avant de "checkout"(= vous placer) sur votre branche nouvellement créée. Git vous donnera un message d'erreur vous disant que vous ne pourrez pas forcément changer de branche avant d'avoir mis vos changements dans un commit ou autre.

#### Avec l'outil CLI
```bash
git branch <nom-de-la-branche>
```

Ou en créant et basculant dessus immédiatement :
```bash
git checkout -b <nom-de-la-branche>
```

### Changer de branche active
#### Dans SourceGit

#### Avec l'outil CLI

### Fusionner une branche souhaitée dans la branche active
#### Dans SourceGit

#### Avec l'outil CLI

### Lister les branches
#### Dans SourceGit

#### Avec l'outil CLI

### Récupérer un commit spécifique d'une autre branche et le copier sur la branche active
#### Dans SourceGit

#### Avec l'outil CLI

### Résoudre des conflits de fusion post-merge ou pull
#### Dans SourceGit

#### Avec l'outil CLI

## Travailler avec un repo distant
### Tirer les changements du repo distant (pull)
#### Dans SourceGit

#### Avec l'outil CLI

### Récupérer l'historique des commits de toutes les branches sans les télécharger (fetch)
#### Dans SourceGit

#### Avec l'outil CLI

### Pousser les changements sur le repo distant (push)
#### Dans SourceGit
#### Avec l'outil CLI

## Workflow général

## Bonnes pratiques