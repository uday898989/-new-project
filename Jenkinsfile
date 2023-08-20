@Library('brocode-yt') _

pipeline{

    agent any


    stages{
         
        stage('Git Checkout'){
                    
            steps{
            gitCheckout(
                branch: "master",
                url: "https://github.com/uday898989/newproject.git"
            )
            }
        }
        
        stage('Unit Test maven'){
         

             steps{
                script{
                   
                    mvnTest()
                }
             }
         }

         stage('Integration Test maven'){
         

             steps{
                script{
                   
                    mvnIntegrationTest()
                }
             }
         }
         
         stage('static code analysis: sonarqube'){

            steps{
               script{
                   def sonarQubecredentialsId = 'sonar-api'
                   statiCodeAnalysis(sonarQubecredentialsId)
               }
            }
       
         }
     }
         
   }

