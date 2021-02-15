pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                bat 'gradle build'
            }
        }
        stage('Test') {
            steps {
                bat 'gradle -v'
            }
        }
    }

    post {
        always {
            archiveArtifacts artifacts: 'build/libs/**/*.jar', fingerprint: true
            junit 'build/reports/**/*.xml'
        }
    }
}