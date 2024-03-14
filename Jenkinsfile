pipeline {
    agent any
    stages {
        stage('Build') { 
            steps {
                sh 'npm install'
                withSonarQubeEnv(credentialsId: 'sonar',installationName: 'sonar') {
             bat """
                ${scannerHome}/bin/sonar-runner.bat
                pip install -r requirements.txt
            """
            }
        }
    }
}
}
