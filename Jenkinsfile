pipeline {
    agent none
    stages {
        stage('build') {
            agent {
                docker { 
                    image 'maven:3.6.3-openjdk-8-slim'
                    args '-v $HOME/.m2:/root/.m2'
                }
            }
            steps {
               sh 'mvn -v'
               sh 'echo ${JAVA_HOME}'
               sh 'mvn test'
            }
        }
        stage('deploy') {
            agent any
            steps {
               sh 'echo ${JAVA_HOME}'
            }
        }
    }
}
