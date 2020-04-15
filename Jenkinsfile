pipeline {
    agent any
    tools {
        maven 'Maven 3.6.3'
    }
    stages {
        stage('Build') {
            steps {
                slackSend (color: '#FFFF00', message: "STARTED: Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]' (${env.BUILD_URL})")
                withEnv( ["PATH+MAVEN=Maven 3.6.3/bin"] ) {
                    sh 'mvn clean' 
                }
            }
        }
        stage('Test') {
            steps {
                withEnv( ["PATH+MAVEN=Maven 3.6.3/bin"] ) {
                    sh 'mvn test' 
                }
            }
        }
        stage('Package') {
            steps {
                withEnv( ["PATH+MAVEN=Maven 3.6.3/bin"] ) {
                    sh 'mvn package' 
                }
            }
        }
    }
    post {
        success{
            slackSend (color: '#00FF00', message: "SUCCESSFUL: Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]' (${env.BUILD_URL})")
        }
        failure{
           slackSend (color: '#FF0000', message: "FAILED: Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]' (${env.BUILD_URL})") 
        }
    }
}
