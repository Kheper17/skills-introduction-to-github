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

On ajoute un fichier git.md à la branche Master
```
$  git add git.md
On branch Master
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
	new file:   git.md
```
On le Commmit pour l'ajouter
```
$  git commit -m "New branch Master"
[Master b6107c1] New branch Master
 1 file changed, 129 insertions(+)
 create mode 100644 git.md
```

On le pousse en ligne (remote)
```
$  git push origin Master
```
Sur les branches de Git : [Les-branches-avec-Git-Les-branches-en-bref](https://git-scm.com/book/fr/v2/Les-branches-avec-Git-Les-branches-en-bref)


Si on a oublié de faire le commit sur un fichiers, on peut l'ajouter après coup sans refaire un commit
```
$  git add myfile.html
$  git commit --Amend
```

Pour voir ses commit
```
$  git log  // flèche haut et bas, q pour sortir du END
```
---
* git init
* git status
* git add .
* git add -A
* git commit -m ""
* git log            (q pour sortir du END)
* git commit --Amend (ajouter sans refaire un commit)
---

### Pour aller plus loin
* [Les-branches-avec-Git-Les-branches-en-bref](https://git-scm.com/book/fr/v2/Les-branches-avec-Git-Les-branches-en-bref)
* [Commandes-Git-Création-de-branches-et-fusion](https://git-scm.com/book/fr/v2/Commandes-Git-Cr%C3%A9ation-de-branches-et-fusion)
* [La syntaxe markdown](https://docs.framasoft.org/fr/grav/markdown.html)



## Error 
PS F:\GIT-CreaDev\Algorithmique> git status

fatal: detected dubious ownership in repository at 'F:/GIT-CreaDev/Algorithmique'
'F:/GIT-CreaDev/Algorithmique' is on a file system that does not record ownership
To add an exception for this directory, call:
```
$  git config --global safe.directory '*' 
```
https://stackoverflow.com/questions/73485958/how-to-correct-git-reporting-detected-dubious-ownership-in-repository-withou



