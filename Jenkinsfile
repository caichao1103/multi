#!/usr/bin/env groovy

DEBUG = 'debug'
RELEASE = 'release'
PUBLISH = 'publish'

def getBuildTarget() {
    def choices = [DEBUG, RELEASE, PUBLISH]
    return choices.join('\n')
}

pipeline {
    agent any
    parameters {
        string(name: 'RELEASE_NOTE',
                description: '构建描述, 在构建 Release 和 Publish 版本的时候，用户必须输入。',
                defaultValue: '',
                trim: true)
        choice(name: 'BUILD_TARGET',
                choices: getBuildTarget(),
                description: '')

    }
    stages {
        stage('Validate Parameter') {
            steps {
                script {
                    SCM_VARS = checkout scm
                    println SCM_VARS
                    sh 'set'


                }
            }
        }
    }
}