node{
     stage('SCM'){
         //code from git repository
         git 'https://github.com/devopsram/openmrs-core.git'

     }
     stage('Build'){
         //Building the code using maven build tool
         sh 'mvn package'
     }
     stage('Archieve the artifacts'){
         archive 'target/*.jar'
     }

     stage('Sonar qube analysis'){
	   
	   withSonarQubeEnv('sonarqube'){
	   
	         sh 'mvn org.sonarsource.scanner.maven:sonar-maven-plugin:3.2:sonar'
	   }
	 
	 }
}