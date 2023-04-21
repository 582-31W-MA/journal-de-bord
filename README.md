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

## Installation locale

1. Acceptez le devoir sur GitHub Classroom : https://classroom.github.com/a/lIaYn4SY.
2. Cloner le dépôt sur votre ordinateur.
3. Vérifiez que le site fonctionne en exécutant la commande : `php -S localhost:8000 kirby/router.php`. Vous devriez voir la page d'accueil par défaut du _Starterkit_ de Kirby.

## Version PHP

Il se peut que la page affiche une erreur vous indiquant que votre version de PHP n'est pas compatible. Le serveur **webdev.cmaisonneuve.qc.ca** où nous installerons notre gestionnaire de contenu utilise PHP 7.3.31[^1]. Nous devons donc installer une version compatible sur notre poste de travail.

[^1]: Pour des raisons de sécurité, assurez-vous que la version des langages et applications utilisées soit toujours supportée. Par exemple, PHP 7.3 est en fin de vie depuis fin 2021, et est donc vulnérable.

### Mac

1. Téléchargez une version compatible à l'aide de la commande commande `brew install php@8.0`.
2. Dites à `brew` quelle version utiliser : `brew unlink php && brew link php@8.0`. (N'oubliez pas de faire l'opération inverse lorsque vous avez terminé de travailler.)

### Windows

1. Téléchargez PHP 8.0 (version _VS16 x64 Non Thread Safe_) à l'adresse suivante : https://windows.php.net/download#php-8.0
2. Ajoutez PHP à votre PATH.

## Création des utilisateur·rices

### Administrateur·rice

1. Naviguez à l'adresse **localhost:8000/panel**.
2. Entrez les informations suivante :
    - Email : **[codereseau]@cmaisonneuve.qc.ca**
    - mot de passe : **582-31W-MA-22634**

### Éditeur·rice

1. Dans le menu « hamburger » en haut à gauche, cliquez sur « Users ».
2. Cliquez sur « Add new user ».
3. Entrez les informations de votre collègue, et choisissez le rôle « editor ».

## Installation sur le serveur du Collège

Chaque partition du serveur de développement du Collège possède la structure suivante:

-   `/home/<codereseau>` : répertoire personnel (home directory)
-   `/home/<codereseau>/www` : racine des fichiers du serveur web
-   `/home/<codereseau>/logs` : journaux du serveur web et PHP
-   `/tmp` : dossier temporaire (fichiers effacés après 1 jour)
-   `/var/tmp` : dossier temporaire (fichiers effacés après 30 jours)

Nous installerons Kirby dans le dossier `www` afin que le site Web soit disponible à l'adresse **https://[codereseau].webdev.cmaisonneuve.qc.ca**.

Voir https://webdev.cmaisonneuve.qc.ca pour plus d'information au sujet du serveur.

### Accès SSH

Secure Shell (SSH) est un protocole de communication sécurisé qui permet de se connecter à distance à un ordinateur afin d'obtenir un shell ou ligne de commande.

Pour vous connecter à votre partition du serveur de développement du Collège, il suffit d'exécuter la commande suivante :

```sh
ssh <codereseau>@webdev.cmaisonneuve.qc.ca
```

### Créer un dossier `journal-de-bord`

Une fois connecté au serveur du Collège via SSH, naviguez dans le dossier `www` et créez-y une nouveau dossier nommé `journal-de-bord`.

Rappelez-vous, la commande pour changer de répertoire est `cd`. La commande `ls` permet d'afficher le contenu du répertoire dans lequel vous êtes présentement, et la commande `mkdir` permet de créer un nouveau répertoire.

### Transfert de fichiers

Nous utiliserons SCP pour transférer les fichiers de votre installation Kirby sur le serveur de développement du Collège. Exécutez la commande suivante :

#### Mac

```sh
scp -r "chemin/vers/dépôt/(*|.*)" <codereseau>@webdev.cmaisonneuve.qc.ca:www/journal-de-bord
```

#### Windows

Puisque l'implémentation de SCP sur Windows diffère de celle sur Mac et Linux, il faut transférer nos fichiers en 2 parties. D'abord exécuter la commande suivante :


```sh
scp -r "chemin/vers/dépôt/*" <codereseau>@webdev.cmaisonneuve.qc.ca:www/journal-de-bord
```

Puis, pour transférer les fichiers cachés :

```sh
scp -r "chemin/vers/dépôt/.*" <codereseau>@webdev.cmaisonneuve.qc.ca:www/journal-de-bord
```

Votre site Web devrait maintenant être accessible à l'adresse suivante : **https://[codereseau].webdev.cmaisonneuve.qc.ca/journal-de-bord**.

## Synchroniser votre environnement de développement et votre serveur avec Git

Puisque nous avons dupliqué tous les fichiers du dépôt sur le serveur, votre répertoire devrait déjà être initialisé avec Git. Pour en être sûr, exécuter la commande suivante dans votre répertoire `www/journal-de-bord` :

```sh
git status
```

Dorénavant, il vous suffira de `git pull` ou `git push` sur votre serveur les changements effectués dans votre environnement de travail local, et vice versa.

### Authentification GitHub

Il est fort probable que vous aillez à vous authentifier afin de pouvoir interagir avec votre dépôt GitHub à partir du serveur. Pour des raisons de sécurité, GitHub requiert l'utilisation d'un _personal access token_ comme mot de passe. Pour créer un _personal access token_, suivez les instructions disponibles à l'adresse suivante, **et n'oubliez pas de sauvegarder votre _personal access token_** : https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token

## Accéder au serveur du Collège à distance

Le serveur du Collège est accessible de l'extérieur du Collège à partir d’une passerelle OpenVPN. Consulter la procédure d'installation du VPN pour votre plateforme :

-   [Mac](https://webdev.cmaisonneuve.qc.ca/pdf/webdev-vpn-mac.pdf)
-   [Windows](https://webdev.cmaisonneuve.qc.ca/pdf/webdev-vpn-windows.pdf)

Une fois active, la connexion VPN vous permettra d'accéder au serveur via SSH ainsi qu'à votre site Web.

## Soumettre les entrées du journal

À chaque semaine, vous devrez soumettre votre entrée via le CMS de l'un ou l'une de vos collègues. Si vous avez suivi les instructions ci-haut, vous devriez pouvoir vous connecter au panel de celui-ci à l'adresse suivante : **https://<codereseau-de-votre-collègue>.webdev.cmaisonneuve.qc.ca/journal-de-bord/panel**.

## Critères d'évaluation

| Critère | Points |
| ------- | ------ |
| Remise  | 3      |
