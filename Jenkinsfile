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
