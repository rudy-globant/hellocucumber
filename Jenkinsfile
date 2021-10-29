pipeline {
    agent none
    stages {
        stage('build') {
            agent {
                docker { image 'maven:3.6.3-openjdk-8-slim' }
            }
            steps {
               sh 'mvn -v'
               sh 'java --version'
               //sh 'now=`date`; echo "<h1>${now}</h1>" > now.html'
            }
        }
        stage('deploy') {
            agent any
            steps {
               sh 'echo ${JAVA_HOME}'
               //sh 'docker cp now.html static_files:/app/public'
            }
        }
    }
}
