pipeline {
    agent any
    tools {
        maven 'Maven 3.6.3'
    }
    stages {
        stage('Build') {
            steps {
                withEnv( ["PATH+MAVEN=M3/bin"] ) {
                    sh 'mvn clean' 
                }
            }
        }
        stage('Test') {
            steps {
                withEnv( ["PATH+MAVEN=M3/bin"] ) {
                    sh 'mvn test' 
                }
            }
        }
        stage('Package') {
            steps {
                withEnv( ["PATH+MAVEN=M3/bin"] ) {
                    sh 'mvn package' 
                }
            }
        }
        stage('Deploy') {
            steps {
                withEnv( ["PATH+MAVEN=M3/bin"] ) {
                    sh 'mvn deploy' 
                }
            }
        }
    }
}
