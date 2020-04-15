pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                withMaven(maven : "Maven 3.6.3"){
                    sh 'mvn clean' 
                }
            }
        }
        stage('Test') {
            steps {
                withMaven(maven : "Maven 3.6.3"){
                    sh 'mvn test' 
                }
            }
        }
        stage('Package') {
            steps {
                withMaven(maven : "Maven 3.6.3"){
                    sh 'mvn package' 
                }
            }
        }
        stage('Deploy') {
            steps {
                withMaven(maven : "Maven 3.6.3"){
                    sh 'mvn deploy' 
                }
            }
        }
    }
}
