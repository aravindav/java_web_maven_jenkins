@Library('jenkins-shared-library') _
pipeline{

    agent any 

    stages {

        
        stage('Gt Checkout'){
            steps {
                script {
                    gitCheckout(branch : "main", url : "https://github.com/aravindav/java_web_maven_jenkins.git")
                }
            }
        }

        stage('Unit Test Maven'){
            steps{
                script {
                     mvnTest()
                }
            }
        }

    }
}