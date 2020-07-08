pipeline
{
  agent any
  options {
    skipDefaultCheckout true
  }

   stages
   {
	stage("checkout code")
		{
		steps
		{
		
		git 'https://github.com/sravankumar-n/game-of-life.git'
		
		}
		}
		
		stage("start build")
		{  
		steps
		{
			sh 'mvn package'
        }
        }
		stage("upload war to Nexus")
		{
		  steps{
		  
		  nexusArtifactUploader artifacts: [[
		  
		  artifactId: 'gameoflife', 
		  classifier: '', 
		  file: 'gameoflife-web/target/gameoflife.war', 
		  type: 'war']], 
		  credentialsId: 'nexus3', 
		  groupId: 'demo',
		  nexusUrl: '172.31.7.111:8081',
		  nexusVersion: 'nexus3', 
		  protocol: 'http', 
		  repository: 'maven-releases',
		  version: '1.0-SNAPSHOT'
		    	 }
		}
		}
		
		}
		
