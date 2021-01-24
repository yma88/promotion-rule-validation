pipeline {
    agent none
    stages {
        stage('Rule Format Test'){
            agent { label 'maven' }
            steps {
                script {
                    try {
                        sh script: "mvn clean install"
                        sh script: "java -jar target/promotion-rule-validation-1.0-SNAPSHOT.jar"
                    }
                    catch (exc) {
                        error("Rule format test failed.")
                    }
                }
            }
        }
    }
}