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
                sh "sudo docker build . -t tomcatwebapp:${env.BUILD_ID}"
            }
        }
    }
}