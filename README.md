# Partie 1

## Problèmes rencontrés

- Il faut ajouter les participants comme collaborateurs pour qu'ils puissent travailler sur le repository.

- On doit push tout ce qu'on fait pour que ce soit visible pour les autres

## Commandes
Créer une branche :
```console
git branch "nom"
```
Lister les branches :
```console
git branch -a
```
Ajouter tous les fichiers au commit :
```console
git add *
```
Créer un commit :
```console
git commit -m "description"
```
Push le commit :
```console
git push
```
Changer de branche :
```console
git checkout nom
```
Merge deux branches :
```console
git merge nom_branche_a_merge
```
Télécharger les modifications distantes :
```console
git pull
```

# Partie 2

## Situation 1
### Création d'un repositoy git sur un projet existant

Dans le projet local existant on crée un environnement git :
```console
git init
```

On créer un repo vide sur github et on ajoute le collaborateur B

On lie le repo github à l'environnement git initialisé :
```console
git remote add origin "lien du repo github"
```
On crée une branche main :
```console
git branch -M main
```

### On fait le premier commit et push :
```console
git add *
git commit -m "first commit"
git push --set-upstream origin main
```
## Situation 2

On crée un repository git, on ajoute le collaborateur B, on créer les fichiers/dossiers nécéssaires, le collaborateur B créer les différents commits corrects et éronnés.

Je crée une issue mentionnant le problème directement sur github.com.

Le collaborateur B me répond en mentionnant le commit qui pose problème et le dernier commit fonctionnel, pour les mentionner, il suffit de copier/coller le numéro de commit.

On retourne au commit donné par le collaborateur B :

```console
git reset --hard "ref du commit"
git add *
git commit -m "restore working version"
git push -f
```

Pour refaire les changements sur le repository du collaborateur B :

```console
git pull --rebase
echo "autre changement de B" > Dossier_B/textB2.txt
git add *
git commit -m "ajout de textB2.txt"
git push
```

Tout est bon !