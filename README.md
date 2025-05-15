<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <title>Gestion d’une Compagnie Aérienne – Mini Projet SGBD</title>
    <style>
        body {
            font-family: "Segoe UI", Tahoma, Geneva, Verdana, sans-serif;
            background-color: #f9f9f9;
            color: #333;
            line-height: 1.6;
            margin: 0;
            padding: 0 15px;
        }

        header {
            background-color: #004080;
            color: white;
            padding: 20px 0;
            text-align: center;
        }

        h1 {
            font-size: 2em;
            margin-bottom: 0;
        }

        h2 {
            color: #004080;
            border-bottom: 2px solid #004080;
            padding-bottom: 5px;
            margin-top: 40px;
        }

        h3 {
            color: #0066cc;
            margin-top: 25px;
        }

        ul {
            margin-left: 25px;
        }

        p {
            max-width: 900px;
        }

        code {
            background-color: #eee;
            padding: 2px 5px;
            border-radius: 3px;
        }

        footer {
            text-align: center;
            font-size: 0.9em;
            margin-top: 40px;
            padding: 20px 0;
            color: #666;
        }

        .container {
            max-width: 960px;
            margin: auto;
            padding: 20px;
            background-color: white;
            box-shadow: 0 0 10px rgba(0,0,0,0.1);
            margin-top: 30px;
        }
    </style>
</head>
<body>
    <header>
        <h1>Gestion d’une Compagnie Aérienne – Mini Projet SGBD</h1>
    </header>

    <div class="container">
        <h2>📌 Contexte</h2>
        <p>
            Ce projet a été réalisé dans le cadre du module Systèmes de Gestion de Base de Données (SGBD) à l’ISG de Tunis.
            Il s’inscrit dans une démarche de modernisation du système d'information d'une compagnie aérienne fictive.
            L’objectif principal est la conception, la création et la gestion d’une base de données Oracle permettant
            d’assurer le suivi des opérations clés : gestion des vols, réservations, passagers, aéroports, personnel et utilisateurs.
        </p>

        <h2>🎯 Objectifs du Projet</h2>
        <ul>
            <li>Créer un modèle relationnel cohérent et complet.</li>
            <li>Implémenter des requêtes SQL et PL/SQL répondant à des besoins métier spécifiques.</li>
            <li>Gérer les utilisateurs et leurs privilèges selon leurs rôles.</li>
            <li>Appliquer des règles de gestion et automatiser certains comportements critiques.</li>
            <li>Permettre l’accès multi-schémas via des droits et des vues.</li>
        </ul>

        <h2>🧩 Modèle Relationnel</h2>
        <p>La base de données comprend les tables suivantes :</p>
        <ul>
            <li><code>AVION(id_avion, modele, capacite, type)</code></li>
            <li><code>AEROPORT(id_aeroport, nom, ville, pays)</code></li>
            <li><code>VOL(id_vol, date_depart, heure_depart, heure_arrivee, id_avion, aeroport_depart, aeroport_arrivee)</code></li>
            <li><code>PASSAGER(id_passager, nom, prenom, email, telephone)</code></li>
            <li><code>RESERVATION(id_reservation, id_passager, id_vol, date_reservation, statut)</code></li>
            <li><code>EMPLOYE(id_employe, nom, prenom, poste, email)</code></li>
            <li><code>ASSIGNATION_EQUIPAGE(id_vol, id_employe, role)</code></li>
            <li><code>BAGAGE(id_bagage, poids, id_reservation)</code></li>
            <li><code>PRESENCE_VOL(id_passager, id_vol, etat_presence)</code></li>
            <li><code>UTILISATEUR(id_user, login, mot_de_passe, profil)</code></li>
        </ul>

        <h2>⚙️ Fonctionnalités Implémentées</h2>

        <h3>Création de la base de données</h3>
        <ul>
            <li>Schéma relationnel avec clés primaires/étrangères et contraintes.</li>
            <li>Insertion d'exemples de données.</li>
        </ul>

        <h3>Gestion des utilisateurs Oracle</h3>
        <p>Création de profils :</p>
        <ul>
            <li>Administrateur</li>
            <li>Agent de réservation</li>
            <li>Personnel navigant</li>
            <li>Attribution de privilèges adaptés.</li>
        </ul>

        <h3>Requêtes SQL Métier</h3>
        <ul>
            <li>Recherche de vols disponibles.</li>
            <li>Liste des passagers absents.</li>
            <li>Calcul du poids total des bagages.</li>
            <li>Taux d’occupation des vols, etc.</li>
        </ul>

        <h3>Règles de gestion</h3>
        <ul>
            <li>Création et annulation de réservations.</li>
            <li>Vérification des doublons.</li>
            <li>Interdiction de chevauchements de vols pour un employé.</li>
        </ul>

        <h3>Automatisations</h3>
        <ul>
            <li>Génération automatique de bagage à la réservation.</li>
            <li>Sécurisation des mots de passe.</li>
            <li>Contrôle d'intégrité métier.</li>
        </ul>

        <h3>Partage inter-schémas</h3>
        <ul>
            <li>Mise en place de vues, synonymes et droits d'accès.</li>
        </ul>

        <footer>
            <p><strong>Date de rendu :</strong> 02/05/2025</p>
        </footer>
    </div>
</body>
</html>
