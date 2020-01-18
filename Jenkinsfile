pipeline{
   agent any
   stages{
     stage('---clean---'){
        steps{
           def=mvnHome = tool name: 'maven-3', type: 'maven'
           sh "${mvnHome}/bin/mvn clean"
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
