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
                    SCM_VARS = git url: 'git@github.com:caichao1103/multi.git', credentialsId: 'ssh-caichao-pc'
                    println(SCM_VARS)
                    sh "git status"
                    println(env.BRANCH_NAME)

                }
            }
        }
    }
}