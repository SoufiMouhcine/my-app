pipeline{
agent any
        tools{
        maven 'Maven'
        jdk 'java_8'
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
                
                  }
               }                   
}
