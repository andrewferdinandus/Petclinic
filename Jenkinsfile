pipeline {
    agent any
    tools {
        jdk 'jdk'
        maven 'maven'
    }

    stages {
        stage('Git Checkout') {
            steps {
                git branch: 'feature-1', changelog: false, poll: false, url: 'https://github.com/andrewferdinandus/Petclinic.git'
            }
        }
        
        stage('Compile') {
            steps {
                sh "mvn clean compile"
            }
        }
        
        stage('Build') {
            steps {
                sh "mvn clean package"
            }
        }
        
        
    }
}
