pipeline {
    agent { label 'Jenkins-Agent' }
    tools {
        jdk 'java11'
        maven 'maven'
    }
    stages{
        stage("Cleanup Workspace"){
            steps {
            cleanWs()
            }
        }
        stage("Checkout from SCM"){
            steps {
                git branch: 'main', credentialsId: 'github', url: 'https://github.com/Seenu4512/registration-app.git'
            }
        }
        stage("Build Application"){
            steps {
                sh "mvn clean package"
        
            }
            
        }
        stage("Test Application"){
            steps {
                sh "mvn test"
            }
        }
    }
}
