pipeline {
    agent any

    stages {

            stage('Complile Stage') {
                steps {
                    withMaven(maven: 'mavenn') {
                        sh 'mvn compile'
                    }
                }
            }

            stage('Test Stage') {
                steps {
                    withMaven(maven: 'mavenn') {
                        sh 'mvn test'
                    }
                }
            }

            stage('Cucumber Reports') {
                steps {
                    cucumber buildStatus: "UNSTABLE",
                        fileIncludePattern: "**/cucumber.json",
                        jsonReportDirectory: 'target'
                }
            }

    }
}