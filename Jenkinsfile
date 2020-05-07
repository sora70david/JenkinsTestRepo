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
               stage("Consolidate Results") {
                      steps {
                               input("Do you want to capture the results?")
                               junit'**/target/surefire-reports/TEST-*.xml'
                               archive'target/*.jar'
                      }      
               }
        }
}
