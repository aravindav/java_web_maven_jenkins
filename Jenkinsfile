@Library('jenkins-shared-library') _
pipeline{

    agent any 

 parameters{
        choice(name: 'action', choices: 'create \ndelete', description:'Choose create/destroy')
    }


    stages {

        stage('Gt Checkout'){
         when { expression { param.action == 'create' } }

            steps {
                script {
                    gitCheckout(branch : "main", url : "https://github.com/aravindav/java_web_maven_jenkins.git")
                }
            }
        }

        stage('Unit Test Maven'){
        when { expression { param.action == 'create' } }

            steps{
                script {
                     mvnTest()
                }
            }
        }

        stage('Integration Test maven'){
           when { expression { param.action == 'create' } }

            steps {
                script {
                    mvnIntegrationTest()
                }
            }
        }

    }
}