#!/usr/bin/env groovy

DEBUG = 'debug'
RELEASE = 'release'
PUBLISH = 'publish'

def getBuildTarget() {
    def choices = [DEBUG, RELEASE, PUBLISH]
    return choices.join('\n')
}

pipeline{
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
    stages{
        stage('Validate Parameter') {
            steps {
                script {
                    println "git branch is ${env.GIT_BRANCH}"
                    if (! env.GIT_BRANCH.equals('release')) {
                        println "git branch name is not equal to release"
                    }
                    println "job name is ${env.JOB_NAME}"
                }
                }
        }
		stage('s2') {
			steps {
				echo "stage 2 is done"
			}
		}
    }
}