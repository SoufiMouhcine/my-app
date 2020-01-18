pipeline{
   agent any
   stages{
     stage('---clean---'){
     def mvnHome = tool name: 'Maven', type: 'maven'
         sh "${mvnHome}/bin/mvn clean"
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
