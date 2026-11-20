# Cahier des charges simplifié – ClubChallenge

## 1. Le projet en une phrase

ClubChallenge permet aux clubs sportifs et aux groupes d’amis de lancer des défis, de saisir leurs performances et de suivre un classement, afin de rester motivés sans passer par des messages éparpillés et des tableaux faits à la main.

## 2. Contexte et problème

Aujourd’hui, les petits clubs et les groupes d’amis organisent souvent leurs défis sportifs ou ludiques par messages, à l’oral ou sur des applications de discussion. Les résultats sont parfois difficiles à retrouver, les classements doivent être réalisés manuellement et les performances annoncées ne sont pas toujours vérifiées.

ClubChallenge a pour objectif de centraliser ces informations dans une seule application. Chaque groupe pourra organiser ses propres défis, enregistrer les résultats de ses membres et suivre leur progression. Les responsables gagneront du temps dans la gestion des activités, tandis que les participants pourront mieux suivre leurs performances et se motiver grâce aux classements.

## 3. Utilisateurs et rôles

| Rôle           | Qui est-ce ?                                              | Ce qu'il veut faire                                                                                                                                       |
| -------------- | --------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Visiteur       | Toute personne qui arrive sur le site sans être connectée | Découvrir le site, créer un compte ou se connecter. Il ne voit aucun défi ni classement, car les groupes sont privés.                                     |
| Membre         | Toute personne inscrite et connectée                      | Rejoindre des groupes ou en créer, consulter les défis de ses groupes, saisir ses performances, consulter l’historique et les classements de ses groupes. |
| Capitaine      | Un membre qui a créé un groupe                            | En plus de ce que fait un membre : créer et gérer les défis de son groupe, gérer le code d’invitation, valider les performances, exclure un membre.       |
| Administrateur | Le responsable du site                                    | Modérer le site (désactiver un compte ou un groupe), accéder à tous les groupes et consulter le journal d’activité global.                                |

## 4. Fonctionnalités

### Indispensables (première version)

- Compte et connexion : inscription, connexion, déconnexion, avec des droits différents selon le rôle.

- Mes groupes : créer un groupe (le créateur en devient capitaine) ou rejoindre un groupe avec un code d’invitation. Un membre peut appartenir à plusieurs groupes.

- Défis : le capitaine crée des défis (titre, description, discipline, unité, objectif, dates de début et de fin). Un défi peut durer un jour, une semaine, un mois ou toute autre durée.

- Performances : les membres saisissent leurs résultats sur les défis de leurs groupes, sans inscription préalable. Une seule saisie par jour et par défi, dans la période du défi.

- Validation et classement : le capitaine valide ou refuse chaque performance (un refus est justifié). Seules les performances validées comptent dans le classement par défi et par groupe.

### Souhaitables (si le temps le permet)

- Notifications : prévenir les membres lorsqu'un résultat est validé ou refusé, lorsqu'un nouveau défi est créé ou lorsqu'un défi approche de sa date de fin.

- Défi du jour proposé automatiquement.

- Commentaires et encouragements sur les défis.

- Modération des commentaires : permettre aux capitaines de modérer les commentaires publiés dans leur groupe. Les administrateurs pourront également intervenir sur l'ensemble du site afin de garantir le respect des règles d'utilisation.


### Hors périmètre (ce que l'application ne fera pas)

- Vérifier automatiquement les performances grâce à des montres connectées, des capteurs ou des applications sportives externes.

- Proposer une messagerie instantanée entre les membres.

- Application mobile native.

## 5. Données principales

| Donnée       | Informations                                                                                                     | Liée à                              |
| ------------ | ---------------------------------------------------------------------------------------------------------------- | ----------------------------------- |
| Utilisateur  | Pseudo, adresse e-mail, mot de passe protégé, date d'inscription et état du compte                               | Groupe, appartenances, performances |
| Groupe       | Nom, description, code d'invitation et date de création                                                          | Utilisateur et défi   |
| Appartenance | Membre concerné, groupe rejoint, rôle dans le groupe et date d'adhésion                                          | Utilisateur et groupe               |
| Défi         | Titre, description, discipline, unité de mesure, objectif, date de début et date de fin.                         | Groupe et performances              |
| Performance  | Valeur déclarée, date de déclaration, statut de validation, motif de refus et personne ayant validé le résultat. | Utilisateur et défi                 |

## 6. Pages prévues

- Accueil
- Connexion
- Contact
- Tableau de bord
- Administration

## 7. Contraintes

- Responsive : utilisable sur téléphone et sur ordinateur
- Accessibilité : utilisable au clavier et avec un lecteur d'écran
- Données personnelles : seules les données utiles sont demandées, et les personnes sont informées de leur usage
- Sécurité : les mots de passe seront stockés sous une forme hachée et sécurisée. Les accès aux groupes, aux défis et aux performances seront contrôlés par le serveur.
- Gestion des droits : les actions réservées aux capitaines et aux administrateurs ne devront pas être accessibles aux autres utilisateurs, même en contournant l'interface.

## 8. Technologies prévues

HTML, CSS (Tailwind), JavaScript et React pour l'interface ; Node.js et Express pour le serveur ;
MySQL et MongoDB pour les données ; Docker pour l'environnement.
