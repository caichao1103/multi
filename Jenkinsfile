#!/usr/bin/env groovy

def getTargetEnv() {
    return env.BRANCH_NAME
}

pipeline {
    agent any
    parameters {
        choice(name: 'TARGET_ENV',
                choices: getTargetEnv(),
                description: '测试环境, 线上环境')
    }
    stages {
        stage("A")
        steps {
            script {
                echo "Hello"
            }
        }
    }
}
}