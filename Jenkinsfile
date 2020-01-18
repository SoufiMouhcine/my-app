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
   }
}
