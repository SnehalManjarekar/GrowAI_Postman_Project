pipeline {
    agent any

    stages {

        stage('Checkout Code') {
            steps {
                git 'https://github.com/your-username/your-repo.git'
            }
        }

        stage('Install Newman') {
            steps {
                sh 'npm install -g newman'
                sh 'npm install -g newman-reporter-html'
            }
        }

        stage('Run Postman Tests') {
            steps {
                sh '''
                newman run collection.json \
                -r html \
                --reporter-html-export newman-report.html
                '''
            }
        }

        stage('Archive Report') {
            steps {
                archiveArtifacts artifacts: 'newman-report.html'
            }
        }
    }
}