pipeline {
    agent any
    tools {
        maven "MAVEN3"
        jdk "OracleJDK8"
    }

    stages {
        stage('Fetch code') {
            steps {
               git branch: 'main', url: 'https://github.com/manugowda1/CI-CD-pipeline.git'
            }
        }

        stage('Build'){
            steps{
               sh 'mvn install -DskipTests'
            }

            post {
               success {
                  echo 'Now Archiving it.'
                  archiveArtifacts artifacts: '***/target/*.war'
               }
            }
        }
    }
}