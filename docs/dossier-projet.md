# Dossier de projet – [nom de l'application]

## 1. Compétences mises en œuvre

| Compétence du REAC                                              | Où, dans le projet ?       |
| --------------------------------------------------------------- | -------------------------- |
| Réaliser des interfaces utilisateur statiques web ou web mobile | Page d'accueil (jalon 2)   |
| Maquetter des interfaces utilisateur web ou web mobile          | Dossier captures (jalon 4) |

## 2. Expression des besoins

### Objectifs du projet

ClubChallenge est une application web destinée aux clubs sportifs et aux groupes d'amis qui souhaitent organiser des défis et suivre les performances de leurs membres. Son objectif est de centraliser les informations liées aux défis, aux résultats et aux classements afin de remplacer les échanges dispersés par messages et les tableaux réalisés manuellement.

L'application permettra aux utilisateurs de créer un compte, de se connecter, de créer ou de rejoindre des groupes grâce à un code d'invitation et de participer aux défis proposés. Les membres pourront saisir leurs performances, consulter leur historique et suivre les classements. Les capitaines pourront créer et gérer les défis de leur groupe, valider ou refuser les résultats et gérer les membres.

Des fonctionnalités complémentaires pourront également être développées, comme les notifications, la proposition automatique d'un défi du jour et la possibilité de publier des commentaires et des encouragements sur les défis. Un système de modération des commentaires permettra aux capitaines de supprimer les contenus inappropriés dans leur groupe. Les administrateurs pourront intervenir à l'échelle du site pour assurer le respect des règles d'utilisation.

### Utilisateurs concernés

L'application s'adresse principalement aux clubs sportifs et aux groupes d'amis souhaitant se motiver collectivement grâce à des défis. Quatre types d'utilisateurs sont prévus :

- **Visiteur :** personne non connectée pouvant découvrir le site, créer un compte ou se connecter.
- **Membre :** utilisateur inscrit pouvant rejoindre des groupes, participer aux défis, saisir ses performances et consulter les classements.
- **Capitaine :** membre responsable d'un groupe, pouvant gérer les défis, valider les performances, administrer les membres et modérer les commentaires de son groupe.
- **Administrateur :** responsable du site pouvant modérer l'application, désactiver des comptes ou des groupes et intervenir sur les commentaires à l'échelle globale.

Les groupes étant privés, seuls les utilisateurs autorisés pourront accéder aux défis, aux performances, aux classements et aux commentaires associés à leurs groupes.

### Contraintes du projet

L'application devra être responsive afin de s'adapter aux téléphones, aux tablettes et aux ordinateurs. Les interfaces devront respecter les principes d'accessibilité, notamment la navigation au clavier et l'utilisation avec un lecteur d'écran.

La sécurité et la confidentialité des données devront être prises en compte. Les mots de passe devront être stockés sous une forme hachée et sécurisée. Les données personnelles seront limitées au nécessaire et les droits d'accès aux groupes, aux défis, aux performances et aux fonctions de modération seront contrôlés côté serveur.

### Limites du projet

La première version se concentrera sur les fonctionnalités indispensables : la gestion des comptes et des groupes, la création des défis, la saisie et la validation des performances ainsi que la consultation des classements.

Les notifications, le défi du jour proposé automatiquement, les commentaires et encouragements ainsi que le système de modération des commentaires seront des fonctionnalités complémentaires, développées si le temps disponible le permet.

L'application ne proposera pas de messagerie instantanée, de vérification automatique des performances à l'aide d'objets connectés ni d'application mobile native. Elle sera accessible depuis un navigateur web.

## 3. Environnement technique

(À compléter au jalon 5.)

## 4. Réalisations front-end

### Page d'accueil statique (jalon 2)

- Captures : accueil-mobile.png, accueil-ordinateur.png

- Extrait de code commenté : le formulaire et ses champs accessibles

- Mes choix :
 - Utilisation de Grid pour organiser les champs du formulaire, avec une seule colonne sur mobile et deux colonnes à partir de 1024 px.
 - Utilisation de Flexbox pour disposer verticalement les labels et les champs de saisie.
 - Mise en place de contraintes HTML5 (required, minlength, pattern et type="email") pour vérifier la validité des informations saisies sans JavaScript.
 - Ajout d'indicateurs visuels avec les pseudo-classes :valid et :invalid pour afficher une bordure verte ou rouge selon la validité des champs.
 - Utilisation de aria-describedby pour associer des indications aux champs concernés et de autocomplete pour faciliter la saisie.
 - Adaptation du bouton d'inscription selon la validité du formulaire et ajout d'un texte informatif sur la protection des données personnelles.

### Maquettes (jalon 4)

- Arborescence et parcours principal :
    Le site compte quatre espaces :
    - Pages publiques (Accueil, Connexion, Inscription, Contact, mentions légales, politique de confidentialité)
    - Espace membre (Tableau de bord, Page d'un groupe, Détail d'un défi, Mon profil)
    - Pages réservées au capitaine (créer un défi, performances à valider, gestion du groupe)
    - Administration
    L'arborescence tient sur deux niveaux au plus. Le parcours principal est la déclaration d'une performance : Connexion → Tableau de bord → Détail d'un défi → Saisie d'une performance → Confirmation.

- Maquettes mobile et ordinateur : figma-accueil-mobile.png, figma-accueil-ordinateur.png, figma-tableau-de-bord-mobile.png, figma-tableau-de-bord-ordinateur.png, figma-contact-mobile.png, figma-contact-ordinateur.png

- Schéma d'enchaînement : schema-entrainement.png

- Charte graphique :
  - Palette : bleu nuit #0F1F4B (couleur primaire), orange foncé #C2410C (couleur secondaire), fond de page #F4F6FB, blanc #FFFFFF, texte #1E293B, texte secondaire #475569.
  - Contrastes vérifiés : blanc sur bleu nuit 15,93:1, blanc sur orange foncé 5,17:1, texte sur fond de page 13,52:1, texte secondaire sur fond de page 7:1, orange foncé sur fond de page 4,78:1. Tous dépassent le seuil AA (4,5:1).
  - États des performances : validée ( #166534 sur fond blanc, 7,13:1), refusée ( #B91C1C sur fond blanc, 6,47:1).
  - Typographies : DM Serif Display pour le logo et les titres, Roboto pour
    le texte courant (16 px minimum).
  - Composants : bouton primaire, bouton secondaire, carte de défi avec barre de progression, champ de formulaire, header.

- Mes choix :
 - Palette : L'orange attire l'œil sur l'action principale (saisir une performance, créer ungroupe). J'ai pris un orange foncé plutôt qu'un orange vif pour que le texte blanc reste lisible sur les boutons.
 - Navigation : Un header avec peu de liens, qui change selon que l'utilisateur est visiteur ou membre.
 - Tableau de bord : J'ai fusionné la liste des groupes et les défis en cours sur une seule page, pour éviter une page « Mes groupes » séparée et mettre l'action principale à un clic de la connexion.

- Accessibilité et sécurité prises en compte :
 - Contrastes vérifiés (AA minimum)
 - Information jamais portée par la couleur seule (les statuts ont une icône et un texte)
 - Cibles tactiles d'au moins 44 px
 - Bordure de champ à 4,76:1 pour que les champs restent visibles
 - Un label relié à chaque champ
 - Titres hiérarchisés
 - Focus clavier visible, y compris sur fond bleu nuit
 - Page active signalée dans le menu.
 - Les pages de groupes, de défis et d'administration ne sont accessibles qu'une fois connecté, et selon le groupe d'appartenance
 - Le mot de passe est masqué et ses règles sont affichées dès l'inscription
 - Aucune donnée sensible n'est demandée
 - Le formulaire de contact précise l'usage des données
