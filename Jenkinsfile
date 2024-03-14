pipeline {
    agent any
    stages {
        stage('Build') { 
            steps {
                sh 'npm install'
             //   sh 'npm start'
    
        }
        }
            stage('SonarQube analysis') {
            environment {
                SCANNER_HOME = tool 'sonar';    
            }
                steps {
                withSonarQubeEnv(credentialsId: 'sonar',installationName: 'sonar') {
              sh "${SONAR_HOME}/sonar-scanner -Dsonar.projectKey=myproject1 -Dsonar.sources=src"
            }
        }
    }
}
}
 
