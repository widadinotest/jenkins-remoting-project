pipeline {
    agent any
    stages {
        stage('Vérification du nœud') {
            steps {
                echo "✅ Job lancé sur : ${env.NODE_NAME}"
            }
        }
        stage('Build') {
            steps {
                echo "🔨 Build en cours..."
                echo "Compilation simulée avec succès"
            }
        }
        stage('Tests') {
            steps {
                echo "🧪 Lancement des tests..."
                echo "Test 1 : PASSED"
                echo "Test 2 : PASSED"
                echo "Tous les tests sont passés ✅"
            }
        }
        stage('Déploiement') {
            steps {
                echo "🚀 Déploiement..."
                echo "Application déployée avec succès"
            }
        }
    }
    post {
        success {
            echo "✅ Pipeline terminé avec succès !"
        }
        failure {
            echo "❌ Échec du pipeline !"
        }
    }
}
