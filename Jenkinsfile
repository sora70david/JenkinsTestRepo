pipeline {
       agent any
       stages {
               stage("Cleaning Stage") {
                      steps {
                               bat "test_file_clean"
                      }
               }
               stage("Testing Stage") {
                      steps {
                               bat "test_file_test"
                      }
               }
               stage("Packaging Stage") {
                      steps {
                               bat "test_file_package"
                      }
               }
               stage("Consolidate Results") {
                      steps {
                               input("Do you want to capture the results?")
                               junit'**/target/surefire-reports/TEST-*.xml'
                               archive'target/*.jar'
                      }      
               }
               stage("Email Build Status") {
                      steps {
                             mail body:"${env.JOB_NAME} - Build#${env.BUILD_NUMBER} -${currentBuild.currentResult}\n\nCheck console output at ${env.BUILD_URL} to view the results.", subject:"${env.JOB_NAME} -Build#{env.BUILD_NUMBER} -${currentBuild.currentResult}!!", to:'ddicosmo70@gmail.com'
                      }      
               }              
              
       }       
}
