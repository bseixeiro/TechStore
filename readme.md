# TP TechStore

## Phase 1: Initialisation et Planification

Après avoir créé un dépôt GitHub vide et un token. Les autres membres du groupe fork et le recupèrent en local

```sh
$ git remote add origin git@github.com:bseixeiro/TechStore.git

$ git clone git@github.com:bseixeiro/TechStore.git
```

On rajoute le readme.md :
```sh
$ touch readme.md
```

On l'ajoute et on le commit :
```sh
$ git add .
$ git commit -m "init : readme.md added"
```

Puis on le push sur le repos en github :
```sh
$ git push -u origin main
```
et on lui met un tag de v0:
```sh
$ git tag -a v0.0 -m "Initialisation du projet" 
```
On crée une branche de développement (develop), on bascule dessus, on commit les changements et on le push dans le repos github :

```sh
$ git checkout -b develop

$ git add .
$ git commit -m "readme.md updated"

$ git push -u origin develop
```

Petit problème lors de ce push, un merge de la branche de dev a été fait sur la main. On a donc dû resynchroniser les deux branches avant de continuer.

Pour que tout le monde ai un accès à la branche de développement, on doit récupérer les branches du repos principales:

```sh
$ git remote add upstream git@github.com:bseixeiro/TechStore.git

$ git pull upstream develop
```

**Questions :**

 - Pour l'organisation des branches, nous allons suivre la méthode de Git Flow, notre branche main correspond aux versions de prod de notre site, la branche develop de référence dans l'avancement du projet, c'est ici que l'on ajoute les features une fois terminées. Pour chaque feature on crée une nouvelle branche pour pouvoir travailler en parallèle et une fois fini on merge sur la develop. Avant de merge la branche develop sur la main on fait une branche release/(version), où l'on effectue les phases de test et correction de bug pour la version.Si jamais il y a un problème en prod on crée une branche hotfix basée sur la main où l'on fait les corrections nécessaires avant de remerge sur la main.

*src => https://www.atlassian.com/fr/git/tutorials/comparing-workflows/gitflow-workflow*


![Alt text](./img/brancheShema.png)

 - On se sert essentiellement de ce que nous propose github pour suivre l'avancement du projet en créant des issues avec des tags.

![Alt text](./img/issuesGithub.png)

#### Phase 2: Développement des Fonctionnalités

1. On se créé localement une branche Feature/<tâche> et bascule pour travailler dessus :
```sh
$ git chekout -b Feature/Product 
```

**Questions :**

  - Chacun fait des commits réguliers sur ses branches de features en nommant clairement ce qui a été fait pour ce commit.

![Alt text](./img/featureCommit.png)

  Une fois une feature terminée, on la merge sur la branche develop en gardant la trace de la branche features.

![Alt text](./img/mergeIntoDevelop.png)

  On applique le même principe pour la branche release. 

/* image */

  Pour la branche main on nomme le commit avec le nom de la version du projet.

/* image */

#### Phase 3: Intégration et Tests


**Questions :**

- Quels furent les défis rencontrés lors de la fusion des différentes fonctionnalités ?

Les modifications apportées par les différents membres de notre groupes ont créé plusieurs fois des conflits dans le code, nécessitant une résolution manuelle afin de garantir une cohérence avec nos travaux. 


- Comment avez-vous assuré que le site fonctionne de manière cohérente après les merges ?

Pour s'assurer que le site web fonctionne correctement après les merges, les membres de l'équipe ont examiné les modifications apportées puis nous avons discuté des impacts potentiels et avons assurer que les nouvelles fonctionnalités ne compromettent pas la stabilité du site. 

De plus nous avons essayer de ne pas déployer toutes les fonctionnalités simultanément. Nous avons voulu aborder une approche de déploiement progressif c'est à dire de déployer les changements par étapes, en surveillant les performances et la stabilité de chaque étape. 

Et enfin une communication transparente permet à chacun de comprendre ce qui a été modifié et de signaler rapidement s'il y a un problème. 




#### Conventions de nos commit:
  Les commits jouent un rôle essentiel dans la gestion de versions de notre projet, en fournissant une traçabilité claire des changements effectués au fil du temps. Afin de maintenir une cohérence dans nos messages de commits, nous adoptons une convention standard pour les préfixes et le format global.
  Préfixes:
    FIX:
      Les commits avec le préfixe fix sont utilisés pour corriger des bogues identifiés dans le code. Ces commits sont en corrélation avec les mises à jour de type PATCH dans la gestion sémantique de versions.

    Exemple:
      "fix: resolve issue with user authentication"


    FEAT:
      Les commits avec le préfixe feat introduisent de nouvelles fonctionnalités dans le code. Ils sont associés aux mises à jour de type MINOR dans la gestion sémantique de versions.

    Exemple :
    "feat: implement user profile editing feature"


  Format:
  Chaque message de commit suit le format suivant :

  "<préfixe>: <description brève du changement effectué en Anglais>"
  Exemples:
    Pour l'ajout d'une nouvelle fonctionnalité :
      "feat: implement search functionality"
    Pour la correction d'un bugue :
      "fix: resolve issue with date formatting"