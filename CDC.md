# Cahier des charges du projet de blog

## Contexte

### Présentation / Proposition initiale

Proposition de nom du projet : _oBlog_.  
Au sein d'une école de développement web, un Responsable de formation souhaite donner accès à un _blog interne_ aux élèves.

### Objectif / Contextualisation

Le but du projet est de mettre à disposition un « blog de développeurs » pour que les étudiants qui le souhaitent puissent partager leur parcours de formation. Il s'agit donc d'un projet de blog tout ce qu'il y a de plus standard sur le plan technique, avec comme particularité que le but visé est surtout pédagogique (écriture et partage d'articles en interne dans l'école) :nerd_face:

### Budget

À partir de 2000€ HT (soit 5 [jour/homme](https://fr.wiktionary.org/wiki/jour-homme) pour un [TJM](https://fr.wikipedia.org/wiki/Taux_journalier_moyen) de 400€). Le budget est réparti sur les postes suivants :

- Gestion de projet (étude, cahier des charges, wireframes, suivi du dossier)
- Création de maquettes graphiques originales
- Intégration HTML/CSS
- Développement du blog
- Tests et mise en production (MEP)

### Délai

Deux semaines à compter de la validation du devis (accompagné d'un acompte de 30%).

## Spécifications fonctionnelles

### Apparence

- Ambiance "espace" (cosmos).
- Site responsive, _mobile-first_.

### Contenus

- Des articles
- Des auteurs d'articles
- Des catégories d'articles (déjà connues : Front, Back, Collaboration, Vie du dev).

Les contenus seraient créés _à terme_ via une interface d'administration (à mettre en option dans le devis : dans un premier temps, les contenus seront fournis pour intégration manuelle — prestation de maintenance à prévoir dans le devis).

### Interactions services

- Liens et/ou partages vers les réseaux sociaux.

### Langue(s)

En français uniquement.

### Arborescence

- Accueil
- Page catégorie (articles filtrés par catégorie) :
  - Teamback
  - Teamfront
  - Collaboration
  - MaVieDeDev
- Page article (détail)
- (Contact)
- (Mentions légales)
- (Admin)

![arborescence](arborescence.png)

### Navigation sur le blog

- Un menu principal (_responsive_) vers les catégories et l'accueil.
  - petits écrans : un menu « burger » dans lequel se trouvent les liens
  - sinon : liste de liens visibles
- On clique sur le titre ou l'extrait de texte de l'article pour en afficher le contenu complet.
- On peut cliquer sur une catégorie pour aller sur une page listant tous les articles de cette catégorie.
- Un menu secondaire (dans le footer ou ailleurs) pour lier vers Contact, Mentions légales & Admin.

### Templates / charte graphique

#### Layout global

- Un menu avec :
  - Titre/logo
  - Liens vers les catégories
- Une image d'en-tête avec titre + slogan (baseline)
- "Sidebar" à droite qui regroupe :
  - Champ de recherche
  - Liste des catégories
  - Liste des auteurs
- Pied de page :
  - Liens vers les réseaux sociaux
  - Liens vers admin, contact, mentions légales

#### Liste des articles

- La page d'accueil liste les derniers articles (nombre exact à déterminer).
- Pagination "Précédente" et "Suivante".
- Un article présente :
  - Un titre (cliquable)
  - Un résumé (cliquable)
  - Une date
  - Un auteur
  - Une catégorie

### Contraintes techniques

- Site _responsive_ en _mobile-first_.
- Compatibilité uniquement avec les dernières versions des navigateurs (Chrome, Firefox, Microsoft Internet Explorer 11 et Edge).

## Spécifications techniques

### Architecture logicielle choisie

Le blog sera conçu avec :

#### Côté front

- HTML5 : le code respectera une sémantique correcte.
- CSS : dans sa version 2 ou 3, pour rester compatible avec Internet Explorer 11. L'utilisation d'un framework pour le _responsive_/_mobile-first_ est envisagé.
- JavaScript : sera utilisé si besoin, avec parcimonie néanmoins (pas de fonctionnalités bloquantes).

#### Côté back

- PHP : PHP7 sera utilisé, ainsi que la classe `PDO` pour accéder aux données MySQL.
- MySQL : permettra de stocker & persister les données.

### Description des données

- Articles
  - Titre
  - Résumé
  - Date du publication
  - Nombre de vues
  - Auteur de l'article
  - Catégorie à laquelle appartient l'article
- Auteurs
  - Nom
  - Prénom
  - Image de profil
- Catégories
  - Intitulé