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
            stage('SonarQube analysis') {
            environment {
                SCANNER_HOME = tool 'sonar';    
            }
                steps {
                withSonarQubeEnv(credentialsId: 'sonar',installationName: 'sonar') {
              sh "${SCANNER_HOME}/bin/sonar"
            }
        }
    }
}
}

