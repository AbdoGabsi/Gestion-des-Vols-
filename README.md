# Gestion d’une Compagnie Aérienne – Mini Projet SGBD

## 📌 Contexte

Ce projet a été réalisé dans le cadre du module **Systèmes de Gestion de Base de Données (SGBD)** à l’ISG de Tunis.  
Il s’inscrit dans une démarche de modernisation du système d'information d'une compagnie aérienne fictive.

L’objectif principal est la conception, la création et la gestion d’une base de données Oracle permettant d’assurer le suivi des opérations clés : gestion des vols, réservations, passagers, aéroports, personnel et utilisateurs.

---

## 🎯 Objectifs du Projet

- Créer un modèle relationnel cohérent et complet.
- Implémenter des requêtes SQL et PL/SQL répondant à des besoins métier spécifiques.
- Gérer les utilisateurs et leurs privilèges selon leurs rôles.
- Appliquer des règles de gestion et automatiser certains comportements critiques.
- Permettre l’accès multi-schémas via des droits et des vues.

---

## 🧩 Modèle Relationnel

La base de données comprend les tables suivantes :

- `AVION(id_avion, modele, capacite, type)`
- `AEROPORT(id_aeroport, nom, ville, pays)`
- `VOL(id_vol, date_depart, heure_depart, heure_arrivee, id_avion, aeroport_depart, aeroport_arrivee)`
- `PASSAGER(id_passager, nom, prenom, email, telephone)`
- `RESERVATION(id_reservation, id_passager, id_vol, date_reservation, statut)`
- `EMPLOYE(id_employe, nom, prenom, poste, email)`
- `ASSIGNATION_EQUIPAGE(id_vol, id_employe, role)`
- `BAGAGE(id_bagage, poids, id_reservation)`
- `PRESENCE_VOL(id_passager, id_vol, etat_presence)`
- `UTILISATEUR(id_user, login, mot_de_passe, profil)`

---

## ⚙️ Fonctionnalités Implémentées

### 🛠️ Création de la base de données
- Schéma relationnel avec clés primaires/étrangères et contraintes.
- Insertion d'exemples de données.

### 👥 Gestion des utilisateurs Oracle
Création de profils avec privilèges adaptés :
- **Administrateur**
- **Agent de réservation**
- **Personnel navigant**

### 🔎 Requêtes SQL Métier
- Recherche de vols disponibles.
- Liste des passagers absents.
- Calcul du poids total des bagages.
- Taux d’occupation des vols, etc.

### 🧠 Règles de gestion
- Création et annulation de réservations.
- Vérification des doublons.
- Interdiction de chevauchements de vols pour un employé.

### ⚙️ Automatisations
- Génération automatique de bagage à la réservation.
- Sécurisation des mots de passe.
- Contrôle d'intégrité métier.

### 🔗 Partage inter-schémas
- Mise en place de vues, synonymes et droits d'accès pour permettre la consultation croisée des données.


