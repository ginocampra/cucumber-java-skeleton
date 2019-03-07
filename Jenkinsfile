pipeline {
    agent any
    tools { 
        maven 'Maven3' 
        jdk 'JDK8u202' 
    }
    stages {
        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }
        stage('Install') {
            steps {
                sh 'mvn install'
            }
            post {
                always {
                    junit 'target/surefire-reports/*.xml'
                }
            }
        }
    }
}