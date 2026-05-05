pipeline {
    agent any
    tools {
        jdk 'jdk'
        maven 'maven'
    }

    stages {
        stage('Git Checkout') {
            steps {
                git branch: 'main', changelog: false, poll: false, url: 'https://github.com/andrewferdinandus/Petclinic.git'
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
        
        stage('Deploy'){
            steps {
                sh "cp /root/.jenkins/workspace/petclinic_cicd/target/*.war /opt/apache-tomcat-9.0.65/webapps"
            }
        }
    }
}
