pipeline {
    agent any
    tools { 
        maven 'Maven' 
        jdk 'JDK' 
    }
    stages {
        stage ('Initialize') {
            steps {
                sh '''
                    echo "${PATH}"
                    echo "${M2_HOME}"
                ''' 
            }
        }

        stage ('Build') {
            steps {
                sh 'mvn -Dmaven.test.failure.ignore=true install' 
            }
            post {
                success {
                    junit 'target/surefire-reports/**/*.xml' 
                }
            }
        }
    }
}