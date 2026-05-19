pipeline {
    agent any

    tools {
        ant 'Ant_1.10.x'
    }

    stages {
        stage('Checkout') {
            steps {
                echo 'Code source récupéré.'
            }
        }

        stage('Build') {
            steps {
                echo 'Début du build Ant...'
                bat 'ant clean package'
                echo 'Build Ant terminé.'
            }
        }

        stage('Archive Artifacts') {
            steps {
                echo 'Archivage des artefacts...'
                archiveArtifacts artifacts: 'dist/**', fingerprint: true
                echo 'Artefacts archivés.'
            }
        }
    }

    post {
        success {
            echo 'Build réussi !'
        }
        failure {
            echo 'Build échoué !'
        }
    }
}
