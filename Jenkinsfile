#!/usr/bin/env groovy

@Library("first-shared-lib") _
pipeline {
  agent any
  stages {
    stage("Setup Stage") {
      steps {
        script {
        welcomeJob "lambdatest"
        }
      }
    }
    stage("test groovy") {
      steps {
        script {
          def customImage = "HELLO"
          if ("${customImage}" == 'HELLP') {
            echo 'I only execute on the master branch'
          } else {
            echo 'I execute elsewhere'
            currentBuild.result = 'ABORTED'
            
          }

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
        sh "echo ${params.Environment}"

      }
    }
  }
}
