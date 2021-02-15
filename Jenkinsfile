pipeline {
    agent {
        docker { image 'node:14' }
    }
    stages {
        stage('Test') {
            steps {
                bat 'node --version'
            }
        }
    }
}