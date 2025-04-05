pipeline {
    agent any

    stages {
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
