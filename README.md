# Docker-web

## 📌 Présentation
Ce projet est réalisé dans le cadre d’un **TP Docker Compose**.  
Il a pour objectif de déployer une **stack LAMP** (Linux, Apache, MySQL, PHP) en utilisant **Docker Compose**, avec une architecture basée sur **un service = un conteneur**.

---

## 🧱 Architecture de la stack

- **Apache** (image officielle `httpd`)
  - Sert les fichiers web
  - Communique avec PHP via **PHP-FPM**
- **PHP 8.3** (image construite via un `Dockerfile`)
  - Exécute le code PHP
  - Se connecte à la base de données MySQL
- **MySQL 8**
  - Stocke les données
  - Utilise un **volume Docker** pour la persistance

Chaque service est isolé dans son propre conteneur.

---

## 📂 Arborescence du projet

Docker-web/
├── apache/
│ ├── httpd.conf
│ └── my-vhost.conf
├── php/
│ └── Dockerfile
├── src/
│ └── index.php
├── docker-compose.yml
└── .gitignore


---

## ▶️ Lancer le projet

### Prérequis
- Docker
- Docker Compose (v2)

### Démarrage
```bash
docker compose up -d --build
