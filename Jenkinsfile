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
		}
		}
