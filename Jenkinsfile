pipeline {
    agent any

    stages {
        stage('Récupération du code') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/Yosrianene/SSA12-YosriAnene.git'
            }
        }

        stage('Création du livrable') {
            steps {
                dir('backend') {
                    sh 'mvn clean package -DskipTests'
                }
            }
            post {
                success {
                    archiveArtifacts artifacts: 'backend/target/*.jar', fingerprint: true
                }
            }
        }
    }
}
