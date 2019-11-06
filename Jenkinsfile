pipeline {
   agent any

   tools {
      go 'go 1.13'
   }

   stages {
      stage('Setup') {
          steps {
              // Get some code from a GitHub repository
            git 'https://github.com/190930-UTA-CW-Go/gofundme.git'
            
            sh "go get github.com/190930-UTA-CW-Go/gofundme"
          }
      }
      
      stage('Build') {
         steps {
            // Run Go on a Unix agent.
            sh "go build"
         }

         post {
            success {
               sh "echo BUILD SUCCESS"
            }
         }
      }
      
      stage('Test') {
          steps {
              sh "go test github.com/190930-UTA-CW-Go/gofundme/fund"
          }
          
          post {
              success {
                  sh "echo SUCCESSFUL TEST"
              }
          }
      }
   }
}
