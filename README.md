# 🚀 Jenkins Remoting Project

![Jenkins](https://img.shields.io/badge/Jenkins-2.541.1-D24939?style=for-the-badge&logo=jenkins&logoColor=white)
![Java](https://img.shields.io/badge/Java-17-007396?style=for-the-badge&logo=java&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-Ubuntu-E95420?style=for-the-badge&logo=ubuntu&logoColor=white)
![GitHub](https://img.shields.io/badge/GitHub-Integration-181717?style=for-the-badge&logo=github&logoColor=white)

---

## 📋 Description

Architecture **Jenkins Master-Agent** permettant de distribuer les builds CI/CD sur des machines distantes avec isolation des nœuds. Ce projet démontre la mise en place d'un environnement DevOps complet avec intégration GitHub et pipeline automatisé.

---

## 🏗️ Architecture

```
┌─────────────────────┐         JNLP (port 50000)        ┌──────────────────────┐
│   MASTER (Windows)  │ ◄──────────────────────────────► │  AGENT (Linux Ubuntu) │
│   Jenkins 2.541.1   │                                   │      Label: agent1    │
└─────────────────────┘                                   └──────────────────────┘
          ▲
          │ Webhook
          ▼
   ┌─────────────┐
   │   GitHub    │
   └─────────────┘
```

| Composant | OS | Rôle |
|---|---|---|
| Master | Windows 10 | Orchestration des builds |
| Agent | Linux Ubuntu | Exécution des builds |
| Protocol | JNLP | Communication Master ↔ Agent |

---

## ✅ Ce qui a été réalisé

- 🔧 Installation et configuration de **Jenkins Master** sur Windows 10
- 🔗 Connexion d'un **agent Linux distant** au Master via JNLP (port 50000)
- 🔁 Création d'un **pipeline CI/CD complet** (Build → Tests → Déploiement)
- 🔐 **Isolation des nœuds** pour la sécurité
- 📦 **Distribution des builds** entre architectures Windows et Linux
- 🐙 **Intégration GitHub ↔ Jenkins** via webhooks

---

## 🔄 Pipeline CI/CD

Le pipeline comporte 4 étapes automatisées :

```
✅ Vérification du nœud
        ↓
🔨 Build
        ↓
🧪 Tests
        ↓
🚀 Déploiement
```

```groovy
pipeline {
    agent any
    stages {
        stage('Vérification du nœud') { ... }
        stage('Build')                { ... }
        stage('Tests')                { ... }
        stage('Déploiement')          { ... }
    }
    post {
        success { echo "✅ Pipeline terminé avec succès !" }
        failure { echo "❌ Échec du pipeline !"           }
    }
}
```

---

## 🛠️ Technologies utilisées

| Technologie | Version | Usage |
|---|---|---|
| Jenkins | 2.541.1 | Serveur CI/CD |
| Java | 17 | Runtime Jenkins & Agent |
| Linux Ubuntu | - | OS Agent distant |
| Windows 10 | - | OS Master |
| JNLP | - | Protocole de connexion |
| GitHub | - | Gestion du code source |

---

## 📸 Screenshots

| Agent connecté | Pipeline réussi |
|---|---|
| ![Agent](screenshots/Agent%20conecte.jpeg) | ![Pipeline](screenshots/verification%20de%20pepiline.jpeg) |

| Liaison GitHub-Jenkins | Build vérifié |
|---|---|
| ![GitHub](screenshots/liaison%20entre%20github%20et%20jinkins.jpeg) | ![Build](screenshots/verification%20de%20build.jpeg) |

---

## 🚀 Comment reproduire ce projet

1. **Installer Jenkins** sur une machine Master (Windows ou Linux)
2. **Configurer un nœud agent** dans Jenkins → Manage Jenkins → Nodes
3. **Lancer l'agent** sur la machine distante avec la commande JNLP fournie par Jenkins
4. **Connecter GitHub** via un webhook pointant vers `http://<master-ip>:8080/github-webhook/`
5. **Créer un pipeline** en référençant ce dépôt GitHub

---

## 👤 Auteur

**widadinotest**
🔗 [GitHub](https://github.com/widadinotest/jenkins-remoting-project)

---

> 💡 *Projet réalisé dans le cadre d'une montée en compétences DevOps — CI/CD, Jenkins, intégration continue et déploiement distribué.*
