pipeline {
    agent any
    environment {
        NEXUS_VERSION = "nexus3"
        NEXUS_PROTOCOL = "http"
        NEXUS_URL = "http://localhost:8081/"
        NEXUS_REPOSITORY = "maven-releases"
        NEXUS_CREDENTIAL_ID = "	28479ced-8eb6-4ad7-98df-42e848db9429"
    }
    stages {
        stage ('Compile Stage') {

            steps {
                withMaven(maven : 'Maven3.6') {
                    sh 'mvn clean compile'
                }
            }
        }

        stage ('Testing Stage') {

            steps {
                withMaven(maven : 'Maven3.6') {
                    sh 'mvn test'
                }
            }
        }

    }
}
