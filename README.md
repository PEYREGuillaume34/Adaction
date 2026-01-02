# ADACTION 🌍

**ADACTION** est une plateforme collaborative qui connecte les bénévoles et les associations environnementales autour d'actions de collecte de déchets. Collectez, gagnez des points et contribuez à un monde plus propre !

## 📋 Description

ADACTION permet aux bénévoles de :
- S'inscrire et se connecter de manière sécurisée
- Enregistrer leurs collectes de déchets (mégots, canettes, plastiques, conserves, cannes)
- Accumuler des points en fonction des déchets collectés
- Rejoindre une association environnementale
- Consulter l'historique de leurs collectes
- Gérer leur profil

Les associations partenaires incluent : **Surfrider**, **Greenpeace**, **WWF**, **Zero Waste**, **Sea Shepherd**, et **Les Petits Débrouillards**.

## 🛠️ Technologies utilisées

### Backend
- **Node.js** avec **Express.js**
- **PostgreSQL** (hébergé sur Neon)
- **bcrypt** pour le hashage des mots de passe
- **CORS** pour la gestion des requêtes cross-origin
- **dotenv** pour la gestion des variables d'environnement

### Frontend
- HTML5, CSS3, JavaScript (Vanilla)
- Architecture modulaire avec scripts séparés par page

## 🗄️ Structure de la base de données

La base de données contient 3 tables principales :

- **volunteers** : Informations des bénévoles (username, password hashé, points, localisation, email, association)
- **associations** : Liste des associations partenaires
- **collects** : Historique des collectes avec détail des déchets ramassés et points gagnés

Voir le schéma complet sur [DrawSQL](https://drawsql.app/teams/ada-tech-school-29/diagrams/copy-of-adaction)

## 🚀 Installation et lancement

### Prérequis
- Node.js installé
- Base de données PostgreSQL (Neon)

### Backend
```bash
cd back
npm install
# Créer un fichier .env avec DATABASE_URL
node script.js
```

### Frontend
Ouvrir simplement index.html dans un navigateur ou utiliser un serveur local.

## 📊 Système de points

Les déchets collectés rapportent des points selon cette pondération :
- **Mégot** : 10 points
- **Canne** : 15 points  
- **Canette** : 20 points
- **Plastique** : 30 points
- **Conserve** : 15 points

## 🎯 Fonctionnalités

### Routes API principales

**Bénévoles**
- `GET /volunteers` - Liste tous les bénévoles
- `GET /volunteer/:id` - Détails d'un bénévole
- `GET /volunteer/profile/:id` - Profil complet avec association
- `POST /volunteer` - Inscription d'un nouveau bénévole
- `PUT /volunteer/:id` - Modification du profil
- `PUT /volunteer/points/:id` - Ajout de points après collecte
- `DELETE /volunteer/:id` - Suppression d'un compte

**Collectes**
- `POST /postCollects` - Enregistrement d'une nouvelle collecte
- `GET /collects` - Liste des collectes
- `GET /collects/:volunteer_id` - Historique des collectes d'un bénévole

**Associations**
- `GET /associations` - Liste des associations

### Pages Frontend
- **index.html** : Page d'accueil
- **register.html** : Inscription
- **userLogin.html** : Connexion
- **profile.html** : Profil du bénévole
- **edit-profile.html** : Modification du profil
- **historique.html** : Historique des collectes
- **wip.html** : Nouvelle collecte
- **assos.html** : Présentation des associations
- **total.html** : Statistiques globales

## 📐 Schémas du projet

- [Schéma de base de données (DrawSQL)](https://drawsql.app/teams/ada-tech-school-29/diagrams/copy-of-adaction)
- [Architecture du projet (Excalidraw)](https://excalidraw.com/#json=Vk9DiZdGhYchYMoUUUFUn,BvYIlsiuiI8WtOkHo7iXZA)

## 📝 Journal de développement

### 29/09/2025
- Schématisation de la base de données sur DrawSQL
- Initialisation du serveur
- Création de la première route `GET /Volunteers`

### 30/09/2025
- Création de la route `GET /Volunteers/Location`

### 1/10/2025
- Pages Asso et Collecte/Type créées (DOM)
- CRUD des Volunteers

### 2/10/2025
- POST type implémenté
- Tables modifiées
- Organisation des tâches

## 👥 Équipe

Projet réalisé dans le cadre de la formation Ada Tech School.

