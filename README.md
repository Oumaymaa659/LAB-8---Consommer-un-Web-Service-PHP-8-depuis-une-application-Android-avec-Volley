# 📱 Student Management System - Full Stack Android & PHP

Ce projet est un laboratoire complet (Lab) démontrant la mise en œuvre d'une architecture **Client-Serveur**. Il s'agit d'une application Android permettant de gérer des étudiants en communiquant avec une base de données MySQL distante via des Web Services PHP.

---

## 📺 Démonstration

#### Option A : GIF Animé (Directement visible)
> **Instructions pour [Ton Nom] :** Enregistre une démo de 10s, convertis-la en GIF (ex: `demo.gif`), place ce fichier à la racine de ce dépôt, puis décommente la ligne ci-dessous.

#### Option B : Lien Vidéo (YouTube / Drive)

https://github.com/user-attachments/assets/7c592509-a182-4b5c-bd32-dfc2ff90a6ea

---

## 🚀 Fonctionnalités
* **Interface Android :** Saisie des informations (Nom, Prénom, Ville, Sexe) via une interface utilisateur intuitive.
* **Consommation d'API :** Utilisation de la bibliothèque **Volley** pour envoyer (POST) et récupérer (GET) des données de manière asynchrone.
* **Backend RESTful :** API développée en **PHP 8** retournant des données structurées au format **JSON**.
* **Persistance des données :** Stockage sécurisé dans une base de données **MySQL**.
* **Tests API :** Validation des points d'accès (endpoints) via **Advanced REST Client (ARC)**.

## 🛠️ Stack Technique
* **Mobile :** Android Studio (Java), Volley, Gson.
* **Serveur :** PHP 8, PDO (PHP Data Objects).
* **Base de données :** MySQL (hébergé via XAMPP).
* **Format de données :** JSON.

---

## 📂 Structure du Projet

### 1. Base de données (MySQL)
La base `school1` contient une table `Etudiant` structurée comme suit :
* `id` (INT, Primary Key, Auto-increment)
* `nom` (VARCHAR)
* `prenom` (VARCHAR)
* `ville` (VARCHAR)
* `sexe` (VARCHAR)

### 2. Web Service (PHP)
Le backend est organisé de manière modulaire pour une meilleure maintenance :
* `connexion/Connexion.php` : Classe Singleton gérant la connexion sécurisée à la BDD via PDO.
* `classes/Etudiant.php` : Modèle de données représentant un étudiant.
* `service/EtudiantService.php` : Logique métier (DAO) pour les opérations CRUD.
* `ws/` : Points d'entrée de l'API (ex: `createEtudiant.php`, `loadEtudiant.php`).

### 3. Application Android
* **Permissions & Sécurité :** Configuration du `AndroidManifest.xml` (permissions Internet) et de `network_security_config.xml` (pour autoriser le trafic HTTP local sur Android 9+).
* **Gestion Réseau :** Implémentation d'une `RequestQueue` pour centraliser les requêtes vers le serveur PHP.
* **Parsing :** Utilisation de Gson pour transformer les objets Java en JSON (et inversement) pour les échanges avec l'API.

---

## ⚙️ Configuration et Installation

### Prérequis
* XAMPP installé (ou équivalent Apache/MySQL).
* Android Studio (version récente).
* Un émulateur Android ou un appareil physique en mode débogage.

### Étapes
1.  **Serveur :** Copiez le dossier contenant vos scripts PHP dans le répertoire `htdocs` de XAMPP (ex: `C:/xampp/htdocs/projet`).
2.  **BDD :** Lancez MySQL via XAMPP, créez la base de données `school1` et la table `Etudiant` (les requêtes SQL sont fournies dans les fichiers du projet).
3.  **Android :**
    * Importez le projet dans Android Studio.
    * **Important :** Dans `AddEtudiant.java`, ajustez l'URL pour pointer vers votre serveur :
        * **Émulateur :** Utilisez `http://10.0.2.2/projet/...`
        * **Appareil Réel :** Utilisez `http://[VOTRE_IP_LOCALE]/projet/...` (votre PC et le téléphone doivent être sur le même réseau).
4.  **Build :** Compilez et lancez l'application.

---

## 🔒 Focus Cybersécurité
En tant qu'étudiante en 4ème année de cybersécurité, ce projet intègre des bonnes pratiques essentielles :
* **Requêtes Préparées :** Utilisation systématique de PDO en PHP pour prévenir les **injections SQL**.
* **Configuration Réseau :** Limitation du trafic en clair (cleartext) via le fichier de sécurité réseau Android.
* **Parsing Sécurisé :** Utilisation de la bibliothèque Gson pour une désérialisation JSON robuste.

---

### Prochaines étapes suggérées
* [ ] Implémenter le CRUD complet (Modification et Suppression d'étudiants).
* [ ] Ajouter une authentification (ex: JWT) pour sécuriser l'accès à l'API.
* [ ] Migration du protocole de HTTP vers HTTPS.

---
**Développé par [Ton Nom]**
*Étudiante en 4ème année de Cybersécurité*
