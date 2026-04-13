pipeline {
    agent any

    tools {
        jdk 'jdk17'
        maven 'maven3'
    }

    stages {
        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Run') {
            steps {
                sh 'nohup java -jar target/java-jenkins-app-1.0.jar > app.log 2>&1 &'
            }
        }
    }
}
