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

## Instruction

### Installation locale

1. Acceptez le devoir sur GitHub Classroom : https://classroom.github.com/a/lIaYn4SY.
2. Cloner le dépôt sur votre ordinateur.
3. Vérifiez que le site fonctionne en exécutant la commande : `php -S localhost:8000 kirby/router.php`. Vous devriez voir la page d'accueil par défaut du _Starterkit_ de Kirby.

### Version PHP

Il se peut que la page affiche une erreur vous indiquant que votre version de PHP n'est pas compatible. Le serveur webdev.cmaisonneuve.qc.ca où nous installerons notre gestionnaire de contenu utilise PHP 7.3.31. Nous devons donc installer une version compatible sur notre poste de travail.

#### Mac

Téléchargez une version compatible à l'aide de la commande commande `brew install php@8.0`. Il suffit ensuite de dire à `brew` quelle version utiliser : `brew unlink php && brew link php@8.0`. (N'oubliez pas de faire l'opération inverse lorsque vous avez terminé de travailler.)

#### Windows

TODO.

### Création des utilisateur·rices

#### Administrateur·rice

1. Naviguez à l'adresse suivante : localhost:8000/panel
2. Entrez les informations ci-bas :

    - Email : **[numéro étudiant·e]@cmaisonneuve.qc.ca**
    - mot de passe : **582-31W-MA-22634**

#### Éditeur·rice

1. Dans le menu « hamburger » en haut à gauche, cliquez sur « Users ».
2. Cliquez sur « Add new user ».
3. Entrez les informations de votre collègue, et choisissez le rôle « editor ».

`scp -r journal-de-bord-maxime-pigeon/(*|.*) mpigeon@webdev.cmaisonneuve.qc.ca:www`

git push auth
personnal access token
