# Intégrer une branche dans la principale
Lorsqu’on développe une nouvelle fonctionnalité, on travaille généralement sur une branche dédiée afin de ne pas perturber la branche principale (souvent master ou main). Une fois la fonctionnalité testée et validée, il faut rapatrier son contenu dans la branche principale. Git propose deux méthodes : fusionner (merge) ou rebaser (rebase).

## Fusionner des branches
Cas simple : fast-forward
Si la branche secondaire est directement issue du dernier commit de la branche principale, Git peut simplement avancer le pointeur de master vers le commit de la branche secondaire.

Commandes :

```bash
git checkout master
git merge nom-de-branche
```
Résultat : un fast-forward (avance rapide).

On peut ensuite supprimer la branche devenue inutile :

```bash
git branch -d nom-de-branche
```
Cas complexe : historique divergent
Si les deux branches ont évolué séparément, Git doit combiner leurs contenus.

Git utilise alors :

 - le dernier commit commun,
 - le dernier commit de chaque branche.
 - Il crée un commit de fusion qui possède plusieurs parents.

-> Dans ce cas, des conflits peuvent apparaître si un même fichier a été modifié différemment dans chaque branche.

Git signale les conflits via git status.

L’utilisateur doit éditer les fichiers concernés, choisir les parties à conserver, puis valider :

```bash
git add fichier_conflit
git commit
```


## Rebaser
Principe
La commande git rebase rejoue les commits d’une branche sur une autre.

Git part du dernier commit commun, puis applique les modifications de la branche secondaire sur la branche principale, dans l’ordre chronologique.

Résultat : un historique linéaire et plus lisible.

Exemple
```bash
git checkout master
git rebase nom-de-branche
```
Différence avec la fusion
Merge : combine deux historiques, crée un commit de fusion.
Rebase : réécrit l’historique en série, sans commit de fusion.

Attention : le rebasage recrée de nouveaux commits (même contenu mais identifiants différents).

Il ne faut jamais rebaser des commits déjà poussés sur un dépôt public, car cela perturbe les autres contributeurs et peut générer des conflits majeurs.

# En résumé
Merge : conserve l’historique parallèle, peut créer des commits de fusion.
Rebase : réécrit l’historique pour le rendre linéaire.

Les deux méthodes aboutissent au même résultat fonctionnel, mais le choix dépend du besoin :

Merge → préserver l’historique complet.
Rebase → obtenir un historique plus clair.
