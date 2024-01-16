# TP TechStore

## Phase 1: Initialisation et Planification

Après avoir créer un dépôts GitHub vide et un token. Les autres membre du groupe le forke et le recupère en local

```sh
$ git remote add origin git@github.com:bseixeiro/TechStore.git

$ git clone git@github.com:bseixeiro/TechStore.git
```

On rajoute le readme.md :
```sh
$ touch readme.md
```

on l'ajoute et on le commit :
```sh
$ git add .
$ git commit -m "init : readme.md added"
```

et on le push sur le repos en github :
```sh
$ git push -u origin main
```

on créé une branche de développement (develop), on bascule dessus, on commit les changements et on le push dans le repos github :

```sh
$ git checkout -b develop

$ git add .
$ git commit -m "readme.md updated"

$ git push -u origin develop
```



