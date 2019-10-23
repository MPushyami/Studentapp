node {
   stage('clone the github repo') {
      git credentialsId: 'github', url: 'https://github.com/supraja12/Studentapp.git'
   }
   stage('maven-clean') {
   sh label: '', script: 'mvn clean'
   }
   stage('maven-compile') {
    sh label: '', script: 'mvn compile'  
   }
   stage('maven-sonar') {
    sh label: '', script: 'mvn sonar:sonar -Dsonar.projectKey=studentapp -Dsonar.host.url=http://10.128.0.7:9000 -Dsonar.login=85edc6b480ac63d4466690cca90bdc1c2749ecec' 
   }
   stage('maven-package') {
    sh label: '', script: 'mvn package'  
   }
   stage('maven deploy-backup to nexus') {
    sh label: '', script: 'mvn deploy'  
   }  
}
