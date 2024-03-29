pipeline {
  agent any
    tools{
      maven 'M2_HOME'
    }
   stages {
    	stage('Git checkout') {
		      steps{
		         echo 'This is first stage of git checkout'
		         git branch: 'main', url: 'https://github.com/Swapnil123321/insure-me.git'
		      }
      	}
      	stage('Create a Package using maven') {
		      steps {
		         echo 'This stage will create a package using maven'
		         sh 'mvn package'
		      }
	    }
	}
}