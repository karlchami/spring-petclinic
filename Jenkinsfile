pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                def mvn_version = 'M3'
                withEnv( ["PATH+MAVEN=${tool mvn_version}/bin"] ) {
                    sh 'mvn clean' 
                }
            }
        }
        stage('Test') {
            steps {
                def mvn_version = 'M3'
                withEnv( ["PATH+MAVEN=${tool mvn_version}/bin"] ) {
                    sh 'mvn test' 
                }
            }
        }
        stage('Package') {
            steps {
                def mvn_version = 'M3'
                withEnv( ["PATH+MAVEN=${tool mvn_version}/bin"] ) {
                    sh 'mvn package' 
                }
            }
        }
        stage('Deploy') {
            steps {
                def mvn_version = 'M3'
                withEnv( ["PATH+MAVEN=${tool mvn_version}/bin"] ) {
                    sh 'mvn deploy' 
                }
            }
        }
    }
}
