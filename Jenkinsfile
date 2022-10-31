pipeline {
    agent any
    options { buildDiscarder(logRotator(numToKeepStr: '2')) }
    tools {
        maven 'devops-maven'
    }
    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
        stage('git integration'){
            steps {
               git branch: 'main', credentialsId: 'jenkins-key', url: 'git@github.com:nizamabad/devops13-maven.git'
            }
        }
        stage('maven build'){
            steps{
                sh 'mvn clean package'
            }
        }
    }
}
