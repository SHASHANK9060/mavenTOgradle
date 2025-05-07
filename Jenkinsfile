pipeline {
    agent any  // Use any available agent

    tools {
        maven 'Maven_3.8.7'  // Ensure this matches the name configured in Jenkins Maven_3.8.7
    }
    stages {
        stage('Checkout') {
            steps {
                git branch: 'master', url: 'https://github.com/SHASHANK9060/mavenTOgradle.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package'  // Run Maven build
            }
        }

        stage('Test') {
            steps {
                sh 'mvn test'  // Run unit tests
            }
        }

        
        
       
        stage('Run Application') {
            steps {
                // Start the JAR application
                sh 'java -jar build/libs/MyMavenApplication-1.0-SNAPSHOT.jar'
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
