
pipeline {
    agent any

    environment {
        IMAGE_NAME = "indian-culture"
        CONTAINER_NAME = "indian-culture-container"
    }

    stages {

        stage('Build Docker Image') {
            steps {
                sh 'docker build --no-cache -t $IMAGE_NAME .'
            }
        }

       stage('Remove Old Container') {
    steps {
        sh '''
        docker rm -f $CONTAINER_NAME || true
        sleep 5
        '''
    }
}

        stage('Run Container') {
            steps {
                sh '''
                docker run -d -p 80:80 --name $CONTAINER_NAME $IMAGE_NAME
                '''
            }
        }
    }
}
