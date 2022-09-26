pipeline {
    agent none 
    stages {
        stage('Build') {
            agent { any 'maven:3.6.3-jdk-11' } 
            steps {
                echo 'Hello, Maven'
                sh 'mvn -B -DskipTests clean package'
            }
        }
        stage('Run') {
            agent { any 'openjdk:11.0.7-jdk-slim' } 
            steps {
                echo 'Hello, JDK'
                sh 'java -jar -Dserver.port=8083 target/demodocker-0.0.1-SNAPSHOT.jar'
            }
        }
    }
}
