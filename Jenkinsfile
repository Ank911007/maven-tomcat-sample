pipeline {
    agent any

    stages {
        
        stage('Compile') {
            steps {
                sh "mvn compile"
                echo 'Compile Sucesss'
            }
        }
        stage('Test') {
            steps {
                sh "mvn test"
                echo 'Test Sucesss'
            }
        }
        stage('Package') {
            steps {
                sh "mvn package"
                echo 'package Sucesss'
            }
        }
        stage('Deploy') {
            steps {
                deploy adapters: [tomcat9(credentialsId: 'tomcat-cred', path: '', url: '<tomcat-url>')], contextPath: 'hello-world', onFailure: false, war: 'target/*.war'
                echo 'deploy Sucesss'
            }
        }
    }
}
