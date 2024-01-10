pipeline {
    environment {
        DOCKER_ID = "m0ph"
        DOCKER_IMAGE_DB = "user-db"
        DOCKER_IMAGE = "user"
        DOCKER_TAG = "${BUILD_ID}"
    }
agent any
    stages {
        stage('Build') {
            steps {
                script {
                    sh '''
                    docker rm -f $DOCKER_IMAGE
                    docker rm -f $DOCKER_IMAGE_DB
                    docker build -t $DOCKER_ID/$DOCKER_IMAGE:$DOCKER_TAG .
                    docker build -t $DOCKER_ID/$DOCKER_IMAGE_DB:$DOCKER_TAG ./docker/user-db
                    '''
                }
            }
        }
    }



}