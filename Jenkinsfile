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
                    println(scm)
                    SCM_VARS = git scm
                    println(SCM_VARS)
                    println("git branch is ${env.BRANCH_NAME}")
                    sh "git checkout branchE; git branch"
                    println("git branch is ${env.BRANCH_NAME}")

                }
            }
        }
    }
}