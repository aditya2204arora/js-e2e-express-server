pipeline {
    agent any
    stages {
        stage('Build') { 
            steps {
                sh 'npm install'
                withSonarQubeEnv(credentialsId: 'sonar',installationName: 'sonar') {
              sh "${SCANNER_HOME}/bin/sonar-scanner"
            }
        }
    }
}
}
