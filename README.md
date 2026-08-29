# 🚚 SafeTransMali

<p align="center">
  <img src="https://raw.githubusercontent.com/laravel/art/master/logo-lockup/5%20SVG/2%20CMYK/1%20Full%20Color/laravel-logolockup-cmyk-red.svg" width="300" alt="SafeTransMali Logo">
</p>

<p align="center">
  <strong>Plateforme moderne de gestion, traçabilité et sécurisation du transport au Mali.</strong>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Laravel-12.x-FF2D20?style=for-the-badge&logo=laravel&logoColor=white" alt="Laravel 12">
  <img src="https://img.shields.io/badge/PHP-%3E%3D8.2-777BB4?style=for-the-badge&logo=php&logoColor=white" alt="PHP 8.2+">
  <img src="https://img.shields.io/badge/Tailwind_CSS-38B2AC?style=for-the-badge&logo=tailwind-css&logoColor=white" alt="Tailwind CSS">
  <img src="https://img.shields.io/badge/Vite-646CFF?style=for-the-badge&logo=vite&logoColor=white" alt="Vite">
  <img src="https://img.shields.io/badge/Licence-MIT-green?style=for-the-badge" alt="License MIT">
</p>

---

## 📌 À Propos de SafeTransMali

**SafeTransMali** est une solution web robuste conçue pour digitaliser, fluidifier et sécuriser la gestion des opérations de transport et de logistique au Mali. Développée avec le framework **Laravel 12**, l'application garantit des performances optimales, une sécurité renforcée et une grande évolutivité.

### 🌟 Fonctionnalités Principales

- 🔐 **Authentification & Gestion des Profils** : Gestion sécurisée des comptes utilisateurs via Laravel Breeze, réinitialisation de mot de passe, vérification d'e-mail et gestion de profil.
- 👥 **Gestion des Clients & Partenaires** : Module dédié à l'administration des clients, suivi des coordonnées et historique.
- 📦 **Suivi & Traçabilité des Transports** : Suivi des expéditions, réservations de trajets et gestion des flux de marchandises en temps réel.
- 📊 **Tableau de Bord Intuitif** : Vue d'ensemble des indicateurs clés (KPIs) pour les administrateurs et gestionnaires.
- ⚡ **Expérience Utilisateur Réactive** : Interface moderne et responsive optimisée pour ordinateurs, tablettes et smartphones avec Tailwind CSS et Vite.

---

## 🛠️ Stack Technique

- **Framework Backend :** [Laravel 12](https://laravel.com)
- **Langage :** PHP 8.2+
- **Frontend & Styling :** Blade, [Tailwind CSS](https://tailwindcss.com), JavaScript (Vite)
- **Authentification :** [Laravel Breeze](https://laravel.com/docs/starter-kits#laravel-breeze)
- **Base de Données :** MySQL / PostgreSQL / SQLite
- **Outils de Qualité de Code :** [Laravel Pint](https://laravel.com/docs/pint) (PSR-12), [PHPUnit](https://phpunit.de)
- **Monitoring Local :** [Laravel Pail](https://laravel.com/docs/pail) (Logs temps réel)

---

## 📋 Prérequis

Avant de commencer, assurez-vous d'avoir installé les outils suivants sur votre environnement de développement :

- **PHP** `>= 8.2` (avec les extensions requises : `mbstring`, `pdo`, `openssl`, `tokenizer`, `xml`, `ctype`, `json`, `curl`)
- **Composer** `>= 2.x`
- **Node.js** `>= 18.x` et **NPM**
- **Base de données** : MySQL 8.x, MariaDB, PostgreSQL ou SQLite
- **Git**

---

## 🚀 Guide d'Installation Rapide

Suivez ces étapes pour installer et configurer le projet localement :

### 1. Cloner le Répertoire

```bash
git clone https://github.com/votre-nom-utilisateur/SafeTransMali.git
cd SafeTransMali
```

### 2. Installer les Dépendances Backend (PHP)

```bash
composer install
```

### 3. Installer les Dépendances Frontend (Node)

```bash
npm install
```

### 4. Configuration de l'Environnement

Dupliquez le fichier `.env.example` pour créer votre configuration locale :

```bash
cp .env.example .env
```

Générez la clé secrète de l'application :

```bash
php artisan key:generate
```

### 5. Configurer la Base de Données

Éditez le fichier `.env` pour renseigner vos identifiants de base de données :

```env
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=safetransmali_db
DB_USERNAME=root
DB_PASSWORD=
```

> 💡 *Note : Pour un démarrage rapide sans serveur MySQL, vous pouvez utiliser SQLite (`DB_CONNECTION=sqlite`).*

### 6. Exécuter les Migrations et Seeders

```bash
php artisan migrate --seed
```

### 7. Créer le Lien Symbolique de Stockage (si fichiers médias/uploads)

```bash
php artisan storage:link
```

---

## 💻 Démarrage en Développement

SafeTransMali inclut un script unifié Laravel 12 pour démarrer en parallèle le serveur web, les workers de file d'attente, les logs et Vite :

```bash
composer run dev
```

*Alternativement, vous pouvez lancer les services manuellement dans des terminaux séparés :*

```bash
# Terminal 1 : Serveur Web Laravel
php artisan serve

# Terminal 2 : Compilation des assets Vite (Hot Reload)
npm run dev

# Terminal 3 (Optionnel) : Écoute des jobs / Queues
php artisan queue:work
```

L'application est ensuite accessible sur : **`http://127.0.0.1:8000`**

---

## 🧪 Tests & Qualité de Code

### Exécuter la Suite de Tests

```bash
# Lancer les tests avec PHPUnit / Artisan Test Runner
php artisan test

# Ou via composer
composer run test
```

### Formater et Nettoyer le Code (Laravel Pint)

```bash
# Vérifier et corriger le style de code selon les standards Laravel / PSR-12
./vendor/bin/pint
```

### Consulter les Logs en Temps Réel

```bash
php artisan pail
```

---

## 📂 Architecture du Projet

```text
SafeTransMali/
├── app/
│   ├── Http/
│   │   ├── Controllers/     # Contrôleurs de requêtes HTTP
│   │   └── Requests/        # Form Requests & validations
│   ├── Models/              # Modèles Eloquent (User, Client, etc.)
│   └── Providers/           # Fournisseurs de services
├── config/                  # Fichiers de configuration de l'application
├── database/
│   ├── factories/           # Usines de génération de données de test
│   ├── migrations/          # Schémas et migrations de la BDD
│   └── seeders/             # Jeux d'essai pour la BDD
├── public/                  # Point d'entrée web (index.php) et assets compilés
├── resources/
│   ├── css/                 # Feuilles de style Tailwind CSS
│   ├── js/                  # Scripts JavaScript (Vite)
│   └── views/               # Vues Blade (layouts, dashboards, auth)
├── routes/
│   ├── web.php              # Routes Web de l'application
│   ├── auth.php             # Routes d'authentification Breeze
│   └── console.php          # Commandes Artisan personnalisées
├── storage/                 # Logs, uploads et caches système
├── tests/                   # Tests unitaires et fonctionnels (Feature/Unit)
├── .env.example             # Exemple de variables d'environnement
├── composer.json            # Dépendances PHP
├── package.json             # Dépendances JavaScript / Vite
└── vite.config.js           # Configuration du bundler Vite
```

---

## 🛡️ Sécurité & Bonnes Pratiques

- **Protection CSRF :** Activée par défaut sur toutes les requêtes Web formulaires.
- **Hachage des Mots de Passe :** Utilisation de l'algorithme sécurisé `bcrypt` / `argon2id`.
- **Validation Strict des Données :** Utilisation des Form Requests Laravel pour filtrer et assainir les entrées utilisateurs.
- **Variables Sensibles :** Ne jamais commiter le fichier `.env` sur Git.

---

## 🤝 Contribution

Les contributions au projet sont les bienvenues ! Pour contribuer :

1. Forkez le projet.
2. Créez une branche dédiée (`git checkout -b feature/ma-fonctionnalite`).
3. Commitez vos modifications (`git commit -m "feat: ajout du module de réservation"`).
4. Poussez votre branche (`git push origin feature/ma-fonctionnalite`).
5. Ouvrez une **Pull Request**.

---

## 📄 Licence

Ce projet est sous licence [MIT](LICENSE). Vous êtes libre de l'adapter selon vos besoins.

---

<p align="center">
  Développé avec ❤️ pour un transport plus sûr et connecté au Mali 🇲🇱.
</p>
