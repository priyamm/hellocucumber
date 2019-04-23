pipeline {
    agent any

    stages {

            stage('Complile Stage') {
                steps {
                    withMaven(maven: 'maven 3.6.1')
                    sh 'mvn clean package'
                }
            }

            stage('Test Stage') {
                steps {
                    withMaven(maven: 'maven_3_6_1')
                    sh 'mvn clean test'
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