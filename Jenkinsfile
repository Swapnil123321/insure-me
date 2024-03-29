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
	    stage('Publish HTML Reports') {
      		  steps {
          			publishHTML([allowMissing: false, alwaysLinkToLastBuild: false, keepAll: false, reportDir: '/var/lib/jenkins/workspace/Insure-me-project/target/surefire-reports', reportFiles: 'index.html',
          			reportName: 'HTML Report', reportTitles: '', useWrapperFileDirectly: true])
              }
        }
        stage('Create a new Docker image') {
	      	steps {
	      		echo 'This stage will create a new docker image from the package Insure-Me.jar file'
	        	sh 'docker build -t unknowndocker811/insurance-app:1.0 .'
	      	}
	    }
	    stage('Login to Dockerhub using stored credentials') {
		    steps {
		        withCredentials([usernamePassword(credentialsId: 'docker-credentials', passwordVariable: 'docker_password', usernameVariable: 'docker_username')]) {
		        	sh 'docker login -u ${docker_username} -p ${docker_password}'
		     	}
			}
		}
	}
}