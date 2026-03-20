pipeline {
    agent any

    stages {
        stage('Clone Code') {
            steps {
                git 'https://github.com/punita-vasani/indian-culture.git'
            }
        }

        stage('Deploy') {
            steps {
                sh '''
                rm -rf /var/www/html/*
                cp -r * /var/www/html/
                '''
            }
        }
    }
}
