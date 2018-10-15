pipeline {
    agent any

    tools {
        maven 'localMaven'
    }

    stages {
        stage('Build') {
            steps {
                sh 'mvn clean package'
                echo "PATH is: $PATH"
                echo "PATH is: $DOCKER_CERT_PATH"
                sh "docker build . -t tomcatwebapp:${env.BUILD_ID}"
            }
        }
    }
}