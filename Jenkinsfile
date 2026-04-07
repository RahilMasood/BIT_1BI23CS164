pipeline {
    agent any

    tools {
        maven 'maven'
    }
    stages {
        stage('Checkout') {
            steps {
                git branch: 'master', url: 'https://github.com/RahilMasood/BIT_1BI23CS164.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }

        
        
       
        stage('Run Application') {
            steps {
                sh 'java -jar target/MyMavenApp-1.0-SNAPSHOT.jar'
            }
        }

        
    }

    post {
        success {
            echo 'Build and deployment successful!'
        }
        failure {
            echo 'Build failed!'
        }
    }
}
