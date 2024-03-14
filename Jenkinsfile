pipeline {
    agent any
    stages {
        stage('Build') { 
            steps {
                sh 'npm install'
                withSonarQubeEnv(credentialsId: 'sonar',installationName: 'sonar') {
             sh "mvn verify sonar:sonar"
            }
        }
    }
}
}
