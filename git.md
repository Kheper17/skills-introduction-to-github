Le site de GIT : https://git-scm.com/, le livre PDF en français!

## Les commandes de base
Qui suis-je ? (whoami)
```
$   whoami
    Mic`
```
pwd (Print Working Directory), affiche votre répertoire de travail, où vous êtes.
```
$   pwd
    /c/Users/Mic
```
CD (Change Directory) pour se déplacer, naviguer.
```
$   CD /D/GIT/
LS (List) afficher ce qu'il y a là où vous êtes. Avec -F il n'affiche que les fichiers.
```
$   LS
     old/ 
     index.html
$   LS -F
     index.html
```
mkdir (Make Directory) créer un dossier.
```
$   mkdir JS
rm -r (remove directory) Effacer un dossier.
```
$   mkdir JS
```



## Paramètrage de Git
Insérer votre nom pour le compte et l'email
```
$ git config --golbal user.name "Kheper17"
$ git config --golbal user.email "mti.android@gmail.com"
```
Pour voir votre conguration
```
$ git config --list
$ git config --list --show-origin
```
Récupérer un dépôt distant
Déplacez vous dans le dossier où vous souhaitez le copier
```
$  cd D:/GIT/
```
Allez sur github sur la branche main du repo qui vous intéresse. Allez dans code et copier dans Clone, HTTPS le lien qui commence par https:// et se termine par .git
```
$  git clone https://github.com/Kheper17/skills-introduction-to-github.git
```
On vérifie
```
$  LS
     skills-introduction-to-github
```     
Ajouter le dépôt distant
```
$  git remote add pb https://github.com/Kheper17/skills-introduction-to-github.git
```
On vérifie
```
$  git remote -v
```
A présent allez dans le dossier télécharger
```
$  cd skills-introduction-to-github
```
On initialise le dépôt git
```
$  git init
```
On ajoute une page nommez git.html (celle-ci en fait).
On va pouvoir ajouter le fichier.
```
$  git add git.html
// git add -A (pour tout ajouter)
```
On vérifie
```
$  git status
```
Ajouter un commit pour le mettre dans le HEAD
```
$  git commit -m "learning file v001"
```
Puis on le pousse sur le distant
```
$  git push origin main
``` 
Souvenez vous on avait ajouter le path dans le dépôt distant (remote).
branch.main.remote=origin dans la config (git config --list)

On peut vérifié en ligne (après 20 secondes).


## Les branches

On crée la branche **Master**
```
$  git branch Master
```
On vérifie
```
$  git log --oneline --decorate
95dcb16 (HEAD -> main, origin/main, origin/HEAD, Master) learning file v003
4c8ccb0 learning file v002
320b548 learning file v001
cd7ebb9 Update to 1 in STEP and README.md
6d21562 Initial commit
```
On est toujours sur HEAD-->main. <br>
On veut aler sur la branche Master
```
$  git checkout Master
```
On vérifie
```
$  git log --oneline --decorate
95dcb16 (HEAD -> Master, origin/main, origin/HEAD, main) learning file v003
4c8ccb0 learning file v002
320b548 learning file v001
cd7ebb9 Update to 1 in STEP and README.md
6d21562 Initial commit
```
Ici on voit le HEAD pointer sur Master