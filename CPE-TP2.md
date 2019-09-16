# CPE - TP2 Bash - Eloi Desbrosses

## Exercice 1. Variables d’environnement

**1. Dans quels dossiers bash trouve-t-il les commandes tapées par l’utilisateur ?**

```
serveur@serveur:~$ printenv PATH
/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games:/snap/bin
```

**2. Quelle variable d’environnement permet à la commande cd tapée sans argument de vous ramener dans
votre répertoire personnel ?**

```
serveur@serveur:~$ printenv
SHELL=/bin/bash
PWD=/home/serveur
LOGNAME=serveur
XDG_SESSION_TYPE=tty
HOME=/home/serveur
LANG=fr_FR.UTF-8
LS_COLORS=rs=0:di=01;34:ln=01;36:mh=00:pi=40;33:so=01;35:do=01;35:bd=40;33;01:cd=40;33;01:or=40;31;01:mi=00:su=37;41:sg=30;43:ca=30;41:tw=30;42:ow=34;42:st=37;44:ex=01;32:*.tar=01;31:*.tgz=01;31:*.arc=01;31:*.arj=01;31:*.taz=01;31:*.lha=01;31:*.lz4=01;31:*.lzh=01;31:*.lzma=01;31:*.tlz=01;31:*.txz=01;31:*.tzo=01;31:*.t7z=01;31:*.zip=01;31:*.z=01;31:*.dz=01;31:*.gz=01;31:*.lrz=01;31:*.lz=01;31:*.lzo=01;31:*.xz=01;31:*.zst=01;31:*.tzst=01;31:*.bz2=01;31:*.bz=01;31:*.tbz=01;31:*.tbz2=01;31:*.tz=01;31:*.deb=01;31:*.rpm=01;31:*.jar=01;31:*.war=01;31:*.ear=01;31:*.sar=01;31:*.rar=01;31:*.alz=01;31:*.ace=01;31:*.zoo=01;31:*.cpio=01;31:*.7z=01;31:*.rz=01;31:*.cab=01;31:*.wim=01;31:*.swm=01;31:*.dwm=01;31:*.esd=01;31:*.jpg=01;35:*.jpeg=01;35:*.mjpg=01;35:*.mjpeg=01;35:*.gif=01;35:*.bmp=01;35:*.pbm=01;35:*.pgm=01;35:*.ppm=01;35:*.tga=01;35:*.xbm=01;35:*.xpm=01;35:*.tif=01;35:*.tiff=01;35:*.png=01;35:*.svg=01;35:*.svgz=01;35:*.mng=01;35:*.pcx=01;35:*.mov=01;35:*.mpg=01;35:*.mpeg=01;35:*.m2v=01;35:*.mkv=01;35:*.webm=01;35:*.ogm=01;35:*.mp4=01;35:*.m4v=01;35:*.mp4v=01;35:*.vob=01;35:*.qt=01;35:*.nuv=01;35:*.wmv=01;35:*.asf=01;35:*.rm=01;35:*.rmvb=01;35:*.flc=01;35:*.avi=01;35:*.fli=01;35:*.flv=01;35:*.gl=01;35:*.dl=01;35:*.xcf=01;35:*.xwd=01;35:*.yuv=01;35:*.cgm=01;35:*.emf=01;35:*.ogv=01;35:*.ogx=01;35:*.aac=00;36:*.au=00;36:*.flac=00;36:*.m4a=00;36:*.mid=00;36:*.midi=00;36:*.mka=00;36:*.mp3=00;36:*.mpc=00;36:*.ogg=00;36:*.ra=00;36:*.wav=00;36:*.oga=00;36:*.opus=00;36:*.spx=00;36:*.xspf=00;36:
SSH_CONNECTION=10.0.2.2 56750 10.0.2.15 22
LESSCLOSE=/usr/bin/lesspipe %s %s
XDG_SESSION_CLASS=user
TERM=xterm-256color
LESSOPEN=| /usr/bin/lesspipe %s
USER=serveur
SHLVL=1
XDG_SESSION_ID=3
XDG_RUNTIME_DIR=/run/user/1000
SSH_CLIENT=10.0.2.2 56750 22
XDG_DATA_DIRS=/usr/local/share:/usr/share:/var/lib/snapd/desktop
PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games:/snap/bin
MAIL=/var/mail/serveur
SSH_TTY=/dev/pts/0
_=/usr/bin/printenv
```

Selon la liste des variables disponibles. J'en déduis qu'il s'agit de la varaible lié au dossier personnel, c'est à dire HOME.

**3. Explicitez le rôle des variables LANG, PWD, OLDPWD, SHELL et _**

```
serveur@serveur:~$ serveur@serveur:~$ printenv LANG
fr_FR.UTF-8
serveur@serveur:~$ printenv PWD
/home/serveur
serveur@serveur:~$ printenv OLDPWD
serveur@serveur:~$ printenv SHELL
/bin/bash
serveur@serveur:~$ printenv _**
```

Selon une (documentation trouvé en ligne)[https://www.computernetworkingnotes.com/rhce-study-guide/linux-environment-variables-list-set-create-remove.html] ces variables ont les rôles suivant:

`LANG` Permet de définir le language préférer.

`PWD` **P**resent **W**orking **D**irectory permet de définir le chemin du dossier de travail actuel.

`OLDPWD` Old **P**rexportesent **W**orking **D**irectory permet de définir l'ancien chemin du dossier de travail actuel. Utile pour la commande `cd -`.

`SHELL` Permet de récupérer le chemin absolus de l'invite de commande actuellement utilisé.

`_` Permet de récupérer la dernière commandé effectué par l'utilisateur.

**4. Créez une variable locale MY_VAR (le contenu n’a pas d’importance). Vérifiez que la variable existe.**

```
serveur@serveur:~$ MY_VAR="salut !"
serveur@serveur:~$ echo $MY_VAR
salut !
```

**5. Tapez ensuite la commande bash. Que fait-elle ? La variable MY_VAR existe-t-elle ? Expliquez. A la fin
de cette question, tapez la commande exit pour revenir dans votre session initiale.**

```
serveur@serveur:~$ bash
serveur@serveur:~$ echo $MY_VAR
serveur@serveur:~$ 
```

la variable n'existe plus. Cela est normale car celle-ci n'est uniquement sauvegardé dans la session actuel. Hors la commande bash crée une nouvelle session bash et switch l'utilisateur sur celle-ci.

**6. Transformez MY_VAR en une variable d’environnement et recommencez la question précédente. Expliquez.**

```
serveur@serveur:~$ export MY_VAR="salut !"
serveur@serveur:~$ printenv $MY_VAR
salut !
serveur@serveur:~$ bash
serveur@serveur:~$ printenv $MY_VAR
salut !
```

Une variable d'environnement est définis dans l'environnement globale. Cela signifie que peu importe la session, la variable sera disponible et utilisable.

**7. Créer la variable d’environnement NOMS ayant pour contenu vos noms de binômes séparés par un espace.
Afficher la valeur de NOMS pour vérifier que l’affectation est correcte.**

```
serveur@serveur:~$ export NOMS="Desbrosses Eloi Amourer Robin"
serveur@serveur:~$ printenv NOMS
Desbrosses Eloi Amourer Robin
```

**8. Ecrivez une commande qui affiche ”Bonjour à vous deux, binôme1 binôme2 !” (où binôme1 et binôme2
sont vos deux noms) en utilisant la variable NOMS.**

```
serveur@serveur:~$ echo "Bonjour à vous deux, $NOMS !"
Bonjour à vous deux, Desbrosses Eloi Amourer Robin !
```

**9. Quelle différence y a-t-il entre donner une valeur vide à une variable et l’utilisation de la commande unset ?**

```
serveur@serveur:~$ export TESTVARIABLE=
serveur@serveur:~$ printenv TESTVARIABLE

serveur@serveur:~$ unset TESTVARIABLE
serveur@serveur:~$ printenv TESTVARIABLE
serveur@serveur:~$
```

Une variable vide est initialisé mais n'as aucune valeur. Une variable unset n'existe pas et ne retourne aucune valeur.

**10. Utilisez la commande echo pour écrire exactement la phrase : $HOME = chemin (où chemin est votre
dossier personnel d’après bash)**

```
serveur@serveur:~$ echo "\$HOME = $HOME"
$HOME = /home/serveur
serveur@serveur:~$
```

## Exercice 2. Contrôle de mot de passe

**Écrivez un script testpwd.sh qui demande de saisir un mot de passe et vérifie s’il correspond ou non au
contenu d’une variable PASSWORD dont le contenu est codé en dur dans le script. Le mot de passe saisi par
l’utilisateur ne doit pas s’afficher.**

```
#!/bin/bash

passwordToCheck="JaimeLesPringles"

#Demande à l'utilisateur un mot de passe

echo "Salut ! Donne moi ton mot de passe svp."

read -s password

if [[ $passwordToCheck = $password ]]; then
        echo "Excellent ! Ton mot de passe fonctionne !"
else
        echo "Aie, ton mot de passe ne correspond pas :("
fi
```

## Exercice 3. Expressions rationnelles

**Ecrivez un script qui prend un paramètre et utilise la fonction suivante pour vérifier que ce paramètre
est un nombre réel :**

```
function is_number()
{
re='^[+-]?[0-9]+([.][0-9]+)?$'
if ! [[ $1 =~ $re ]] ; then
return 1
else
return 0
fi
}
```
**Il affichera un message d’erreur dans le cas contraire.**

```
#!/bin/bash

function is_number()
{
re='^[+-]?[0-9]+([.][0-9]+)?$'
if ! [[ $1 =~ $re ]] ; then
return 1
else
return 0
fi
}


if [ -z "$1" ]; then
        echo "Aucun argument passé"
else

        is_number $1

        if [ $? -eq 0 ]; then
                echo "Ton nombre est réel !"
        else
                echo "Ton nombre n'est pas réel :("
        fi
fi
```

## Exercice 4. Contrôle d’utilisateu
r
**Écrivez un script qui vérifie l’existence d’un utilisateur dont le nom est donné en paramètre du script. Si le
script est appelé sans nom d’utilisateur, il affiche le message : ”Utilisation : nom_du_script nom_utilisateur”,bas où nom_du_script est le nom de votre script récupéré automatiquement (si vous changez le nom de votre
script, le message doit changer automatiquement)**

```
#!/bin/bash

if [ -z "$1" ]; then
        echo "Utilisation : $0 [nom_utilisateur]"
else
        if [[ ! $( id -u $1 2>/dev/null ) ]]; then
                echo "Utilisateur inexistant"
        else
                echo "Utilisateur existant"
        fi
fi
```

## Exercice 5. Factorielle

**Écrivez un programme qui calcule la factorielle d’un entier naturel passé en paramètre (on supposera que
l’utilisateur saisit toujours un entier naturel).**

```
#!/bin/bash

if [ $# -gt "0" ]; then

        resultat=$1

        for i in $(seq $(( $1-1 )) -1 1)
        do
                let resultat=resultat*i
        done


        echo $resultat
else
        echo "Aucun chiffre passé en paramètre"
fi
```

## Exercice 6. Le juste prix

**Écrivez un script qui génère un nombre aléatoire entre 1 et 1000 et demande à l’utilisateur de le deviner.
Le programme écrira ”C’est plus !”, ”C’est moins !” ou ”Gagné !” selon les cas (vous utiliserez $RANDOM).**

## Exercice 7. Statistiques

**1. Écrivez un script qui prend en paramètres trois entiers (entre -100 et +100) et affiche le min, le max
et la moyenne. Vous pouvez réutiliser la fonction de l’exercice 3 pour vous assurer que les paramètres
sont bien des entiers.**

**2. Généralisez le programme à un nombre quelconque de paramètres (pensez à SHIFT)**

**3. Modifiez votre programme pour que les notes ne soient plus données en paramètres, mais saisies et
stockées au fur et à mesure dans un tableau.**

## Exercice 8. Pour les plus rapides

**Écrivez un script qui affiche les combinaisons possibles de couleurs (cf. TP 1) :**
