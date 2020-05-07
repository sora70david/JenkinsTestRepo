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
        }
}
