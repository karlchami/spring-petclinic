pipeline {
    def mvn_version = 'M3'
    agent any
    stages {
        stage('Build') {
            steps {
                withEnv( ["PATH+MAVEN=${tool mvn_version}/bin"] ) {
                    sh 'mvn clean' 
                }
            }
        }
        stage('Test') {
            steps {
                withEnv( ["PATH+MAVEN=${tool mvn_version}/bin"] ) {
                    sh 'mvn test' 
                }
            }
        }
        stage('Package') {
            steps {
                withEnv( ["PATH+MAVEN=${tool mvn_version}/bin"] ) {
                    sh 'mvn package' 
                }
            }
        }
        stage('Deploy') {
            steps {
                withEnv( ["PATH+MAVEN=${tool mvn_version}/bin"] ) {
                    sh 'mvn deploy' 
                }
            }
        }
    }
}
