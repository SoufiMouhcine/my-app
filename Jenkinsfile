pipeline{
   agent any
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
          def mvnHome = tool name: 'Maven', type: 'maven'
         sh "${mvnHome}/bin/mvn package"
       }
     }
   }
}
pipeline{
agent any
        tools{
        maven 'MAVEN 3'
        jdk 'jdk1.8.0_181'
        }
        stages{
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


