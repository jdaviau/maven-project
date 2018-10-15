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
                sh "docker build . -t tomcatwebapp:${env.BUILD_ID}"
            }
        }
    }
}