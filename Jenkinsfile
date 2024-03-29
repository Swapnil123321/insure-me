pipeline {
  agent any
    tools{
      maven 'M2_HOME'
    }
   stages {
    	stage('Git checkouts') {
		      steps{
		         echo 'This is first stage of git checkout'
		         git branch: 'main', url: 'https://github.com/Swapnil123321/insure-me.git'
		      }
      	} 	
	}
}