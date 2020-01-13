pipeline {
    agent any 
    environment {
      mvnHome = "/usr/share/maven"
    }
    tools {
        maven 'Maven3'
    }
    stages {
        stage('git') {
            steps {
                git url: 'https://github.com/albertvo15/cicd5.git'
            }
        }
        stage('Build') {
            steps {
                sh 'mvn clean install'
            }
        }
    }
    post {
        always {
//            archiveArtifacts artifacts: 'build/libs/**/*.jar', fingerprint: true
//            archiveArtifacts artifacts: 'build/**', fingerprint: true
//            archiveArtifacts artifacts: '**', fingerprint: true
//            archiveArtifacts artifacts: 'builds/**', fingerprint: true
//            junit 'build/reports/**/*.xml'
            archiveArtifacts artifacts: '**', fingerprint: true
//            junit 'builds/**/*.xml'
        }
    }
}

