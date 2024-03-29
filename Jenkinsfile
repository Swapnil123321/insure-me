pipeline {
  agent any
    tools{
      maven 'M2_HOME'
    }
   stages {
    	stage('Git checkout') {
		      steps{
		         echo 'This is first stage of git checkout'
		         git branch: 'main', url: 'https://github.com/cbabu85/InsureMe-20Mar.git'
		      }
      	}	
	    stage('Create a Package') {
		      steps {
		         echo 'This will create a package using maven'
		         sh 'mvn package'
		      }
	    }
	}
}