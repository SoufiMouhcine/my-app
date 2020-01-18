pipeline{
   agent any
    tools{
        maven 'Maven'
        jdk 'java_8'
        }
   stages{
     stage('---clean---'){
       steps{
         sh "mvn clean"
       }
     }
     stage('--test--'){
       steps{
         sh "mvn test"
       }
     }
     stage('--package--'){
       steps{
         sh "mvn package"
       }
     }

              stage('build'){
                            steps{
                            bat 'mvn compiler:compile'
                            }
                            post {
                 success {
                   bat "echo 'Projet compilé avec succès'"
                 }
                 failure {
                   bat "echo 'Erreur lors de la compilation du projet'"
                 }
               }
                 }
              stage('Test') {
                steps {
                   bat 'mvn test'
                }
                post {
                  always{
                      junit 'target/surefire-reports/*.xml'
                      }
                   }
                }
                stage('couverture'){
                   steps{
                      bat 'mvn cobertura:cobertura -Dcobertura.report.format=xml'
                      }
                   post{
                     always{
                         cobertura coberturaReportFile: '**/target/site/cobertura/coverage.xml'
                           }
                       }
                  }
               }                   
}
