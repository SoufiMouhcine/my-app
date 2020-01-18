pipeline{
   agent any
   stages{
     stage('---clean---'){
       step{
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



