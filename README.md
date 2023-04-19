# Journal de bord

Le but principal du journal de bord est de vous mettre à la place des utilisateurs et utilisatrices du gestionnaire de contenu que vous mettrai sur pied tout au long de la session. En même temps, les entrées de votre journal serviront de contenu pour les deux travaux pratiques du cours.

Voici le fonctionnement : chaque semaine, du cours 3 au cours 11, vous devrez écrire un court article qui documente une notion de programmation Web vue durant la session. L'entrée doit inclure :

-   un titre
-   une brève explication de la notion
-   sa syntaxe
-   un ou deux exemples
-   ressource(s) à consulter

Inspirez-vous de la documentation disponible ([MDN](https://developer.mozilla.org/fr/), [PHP](https://www.php.net), [MySQL](https://dev.mysql.com/doc/), etc.). Vous ne serez pas évalué·es sur la qualité de l'entrée ; vous pouvez donc citer directement ces sources, en autant que vous donniez la référence.

Dernière modalité : vous écrierez votre article à l'aide du gestionnaire de contenu d'un·e autre élève.

## Instructions

Vous trouverez ci-bas les instructions pour configurer votre environnement de travail local, et pour installer Kirby sur votre propre partition du serveur **webdev.cmaisonneuve.qc.ca**.

### Installation locale

1. Acceptez le devoir sur GitHub Classroom : https://classroom.github.com/a/lIaYn4SY.
2. Cloner le dépôt sur votre ordinateur.
3. Vérifiez que le site fonctionne en exécutant la commande : `php -S localhost:8000 kirby/router.php`. Vous devriez voir la page d'accueil par défaut du _Starterkit_ de Kirby.

### Version PHP

Il se peut que la page affiche une erreur vous indiquant que votre version de PHP n'est pas compatible. Le serveur **webdev.cmaisonneuve.qc.ca** où nous installerons notre gestionnaire de contenu utilise PHP 7.3.31. Nous devons donc installer une version compatible sur notre poste de travail.

#### Mac

1. Téléchargez une version compatible à l'aide de la commande commande `brew install php@8.0`.
2. Dites à `brew` quelle version utiliser : `brew unlink php && brew link php@8.0`. (N'oubliez pas de faire l'opération inverse lorsque vous avez terminé de travailler.)

#### Windows

TODO.

### Création des utilisateur·rices

#### Administrateur·rice

1. Naviguez à l'adresse suivante : localhost:8000/panel
2. Entrez les informations suivante :
    - Email : **[numéro étudiant·e]@cmaisonneuve.qc.ca**
    - mot de passe : **582-31W-MA-22634**

#### Éditeur·rice

1. Dans le menu « hamburger » en haut à gauche, cliquez sur « Users ».
2. Cliquez sur « Add new user ».
3. Entrez les informations de votre collègue, et choisissez le rôle « editor ».

### Installation sur le serveur webdev.cmaisonneuve.qc.ca

Chaque partition du serveur **webdev.cmaisonneuve.qc.ca** possède une structure identique:

-   `/home/<codereseau>` : répertoire personnel (home directory)
-   `/home/<codereseau>/www` : racine des fichiers du serveur web
-   `/home/<codereseau>/logs` : journaux du serveur web et PHP
-   `/tmp` : dossier temporaire (fichiers effacés après 1 jour)
-   `/var/tmp` : dossier temporaire (fichiers effacés après 30 jours)

Nous installerons Kirby dans le dossier `www` afin que votre site Web soit disponible à l'adresse https://<codereseau>.webdev.cmaisonneuve.qc.ca.

#### Accès SSH

`scp -r journal-de-bord-maxime-pigeon/(*|.*) mpigeon@webdev.cmaisonneuve.qc.ca:www`

git push auth
personnal access token
