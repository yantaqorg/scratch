#!/usr/bin/env groovy
@Library('sharedLibrary') _

def REPO = getRepoName()

podTemplate {
    node(POD_LABEL) {
        stage('setup env') {
            sh 'echo setting up env'
            checkout scm
        }
        stage('cat Jenkinsfile') {
            sh 'cat Jenkinsfile'
            sh "echo repo: $REPO"
        }
        stage('test sh echo') {
           def stdout = sh(
                script:"""#!/bin/bash -l
                      ./echo.sh
                    """, 
                    returnStdout: true
          )
        }
    }
}

