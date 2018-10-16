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
                sh 'eval "$(docker-machine env -u)"'
                sh "docker build . -t tomcatwebapp:${env.BUILD_ID}"
            }
        }
    }
}