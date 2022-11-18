pipeline {
    agent any
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
        stage ('Preparation') {
            steps {
                withMaven(maven: 'Maven3.6', mavenSettingsConfig: '5b9c5b2c-9b2a-474b-9464-ccc978b5e252') {
                    sh 'mvn release:prepare -Darguments="-Dcmd.env=dev -Dcmd.parent.sys=soa"'
                    sh 'mvn release:perform -Darguments="-Dcmd.env=dev -Dcmd.parent.sys=soa"'
                }
            }
        }
         
    }
}
