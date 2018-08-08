#!groovy

node {
	   
	stage('Checkouting'){

          checkout scm
       }

       stage('BuildArtifact'){

          sh 'mvn install'
       }
	   
      //stage('Sonar') {
                    //add stage sonar
                    //sh 'mvn sonar:sonar              // }
	
	stage('deploy'){
	sshagent(['tomcat']) {
   		sh 'scp -o StrictHostKeyChecking=no target/*.war ec2-user@172.31.4.35:/opt/apache-tomcat-8.0.53/webapps'
		}
	}
}
