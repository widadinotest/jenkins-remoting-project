# 🚀 Jenkins Remoting Project

## 📋 Description
Architecture Jenkins Master-Agent pour distribuer les builds sur des machines distantes avec isolation des nœuds.

## 🏗️ Architecture
- Master (Windows 10 - Jenkins 2.541.1)
- Agent distant (Linux Ubuntu)
- Connexion : JNLP via port 50000
- Label : agent1

## ✅ Ce qui a été réalisé
- Installation et configuration de Jenkins Master
- Connexion d'un agent Linux distant au Master Windows
- Création d'un pipeline CI/CD qui s'exécute sur l'agent distant
- Isolation des nœuds pour la sécurité
- Distribution des builds entre architectures différentes

## 🛠️ Technologies utilisées
- Jenkins 2.541.1
- Java 17
- Linux Ubuntu
- Windows 10
- JNLP (Java Network Launch Protocol)

## 📸 Screenshots
Ajouter ici vos captures du build et des agents
