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
                sh "docker build . --group-add docker -t tomcatwebapp:${env.BUILD_ID}"
            }
        }
    }
}