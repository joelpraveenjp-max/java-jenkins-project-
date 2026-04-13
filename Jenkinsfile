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
                sh 'java -cp target/java-jenkins-app-1.0.jar com.example.Main'
            }
        }
    }
}
