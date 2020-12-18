#!/usr/bin/env groovy

DEBUG = 'debug'
RELEASE = 'release'
PUBLISH = 'publish'



pipeline {
    agent any
    stages {
        stage('Clone') {
            steps {
                script {
                    SCM_VARS = checkout scm
                    println(SCM_VARS)
                    sh "git status"
                    println(env.BRANCH_NAME)

                }
            }
        }
    }
}