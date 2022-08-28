#!/usr/bin/env groovy
@Library("first-shared-lib") _
pipeline {
  agent any
    stages {
      stage ("Setup Stage") {
        steps {
        welcomeJob "lambdatest"
        }
}
      stage ("test groovy") {
        steps {
        script {
         def customImage = "HELLO"
			if ("${customImage}" == 'HELLP') {
                        echo 'I only execute on the master branch'
                    } else {
                        echo 'I execute elsewhere'
                    }
         
        }
      }
    }
}
}
