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
                sh '''
                    pkill -f "java -jar" || true
                    nohup java -jar target/java-jenkins-app-1.0.jar > app.log 2>&1 &
                    sleep 10
                    cat app.log
                '''
            }
        }
    }
}
