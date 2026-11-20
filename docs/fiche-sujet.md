# Fiche sujet – ClubChallenge

## Le problème (2 ou 3 phrases)
Les petits clubs et groupes d’amis (running, foot, fléchettes, muscu…) organisent leurs défis sur WhatsApp ou à l’oral. Les résultats se perdent, le classement est fait à la main et personne ne peut vérifier les performances annoncées. Les responsables perdent du temps à tout centraliser, et les membres manquent de suivi et de motivation, surtout quand ils sont dans plusieurs groupes à la fois.

## Les utilisateurs et leurs rôles
- Visiteur : consulte la page d’accueil (présentation du site) et peut créer un compte ou se connecter. Il ne voit aucun défi ni classement, car les groupes sont privés.
- Membre :  rejoint des groupes avec un code d’invitation ou crée les siens. Les défis de ses groupes apparaissent sur son tableau de bord, et il saisit ses résultats. Il consulte l’historique et les classements de ses groupes uniquement. Dans chaque groupe, il a un statut :
coéquipier : déclare ses performances, consulte défis et classements ;
capitaine (statut obtenu en créant le groupe) : crée et gère les défis, gère le code d’invitation, valide ou refuse les performances, exclut un membre.
Un même membre peut être coéquipier d’un groupe et capitaine d’un autre.
- Administrateur : modère l’ensemble du site (désactiver un compte ou un groupe), a accès à tous les groupes et consulte le journal d’activité global.

## Les 5 fonctionnalités indispensables
1. Inscription, connexion et gestion des droits (visiteur, membre, administrateur, avec le statut capitaine et l’appartenance contrôlés côté serveur).
2. Page « Mes groupes » : créer un groupe (le créateur en devient capitaine) ou rejoindre un groupe grâce à un code d’invitation.
3. Création et consultation des défis (titre, discipline, unité, objectif, dates) par le capitaine.
4. Déclaration de performances par les membres sur les défis de leurs groupes (sans inscription préalable).
5. Validation des performances par le capitaine et classement par défi et par groupe.

## Les données principales (3 à 5)
- Membre : pseudo, e-mail, mot de passe haché, date d'inscription
- Groupe : nom (unique), description, code d’invitation, date de création.
- Appartenance : membre, groupe, statut dans le groupe, date d'adhésion.
- Défi : titre, description, discipline, unité, objectif, date de début, date de fin.
- Performance : membre, défi, valeur, date, statut (en attente, validée, refusée), motif de refus, validée par.

## Une règle métier
- Un membre ne peut déclarer qu’une seule performance par jour et par défi
- La déclaration doit être dans la période du défi

## Une donnée qui pourrait être stockée en NoSQL
Le journal d’activité (connexion, création de groupe, adhésion par code, création de défi, validation ou refus d’une performance, avec l’auteur, la date et la cible).
