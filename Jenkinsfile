#!/usr/bin/env groovy

@Library("first-shared-lib") _
pipeline {
  agent any
  stages {
  
  stage('Checkout Branch') {
	when {
	   allOf{
              expression {params.BRANCH_NAME != ""}
	   }
	  }
	  steps {
		checkout scm: [$class: 'GitSCM', userRemoteConfigs: [[url: 'https://github.com/shivangi8027/shared-library.git' ]], branches: [[name: params.BRANCH_NAME]]], poll: false
	  }
	  'refs/tags/${TAG}'
	}
   stage('Checkout tag') {
	when {
	   allOf{
	      expression {params.TAG_NAME != ""}
	   }
	  }
	  steps {
		checkout scm: [$class: 'GitSCM', userRemoteConfigs: [[url: 'https://github.com/shivangi8027/shared-library.git' ]], branches: [[name: 'refs/tags/${TAG_NAME}']]], poll: false
	  }

	}
	stage ("copy file"){
	steps {
		sh "cp test2.txt /home/azureuser/mytest45/"
	}
	}
    stage("Setup Stage") {
      steps {
        script {
        welcomeJob "lambdatest"
        }
      }
    }


    stage("test groovy1") {
      when {
        allOf {
          expression {params.Environment == "Stage"}
        }
      }
      steps {
        script {
        sh "echo ${params.Environment}"

      }
      }
    }
  }
}
