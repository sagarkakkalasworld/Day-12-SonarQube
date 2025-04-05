pipeline {
    agent any

    stages {
        stage('SCM Checkout') {
            steps{
           git branch: 'main', url: 'https://github.com/sagarkakkalasworld/Day-12-SonarQube.git'
            }
        }
        // Uncomment the below stage if you configured SonarQube
        stage('Run Sonarqube') {
             environment {
                scannerHome = tool 'sonarqubescanner'
             }
             steps {
                 withSonarQubeEnv(credentialsId: 'sonar-token', installationName: 'sonarqubeserver') {
                     sh "${scannerHome}/bin/sonar-scanner"
                 }
             }
         }

    }
}
