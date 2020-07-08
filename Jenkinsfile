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

ts{
			     def mavenPom = readMavenPom 'pom.xml'
				 nexusArtifactUploader artifacts: [
				 [ 
				 artifactId: 'gameoflife',
				 classifier: '',
				 file: "target/gameoflife.war",
				 type: 'war'
				 ]   
				 ],
				 
				 credentialsId: 'nexus3',
				 groupId: 'com.wakaleo.gameoflife',
				 nexusUrl: '172.31.4.255:8081',
				 nexusVersion: 'nexus3',
		         protocal: 'http',
				 repository: 'maven-releases',
				 version: '1.0-SNAPSHOT'
				 }
		}
		}
		}
