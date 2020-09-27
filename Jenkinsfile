#!/usr/bin/env groovy

def getREG() {
    return dockerBuild.getDockerRegistry()
}

pipeline {
    agent any
    parameters {
        choice(name: 'REG',
                choices: getREG(),
                description: '')
    }
    stages {
        stage("A") {
            steps {
                script {
                    echo "...."
                }
            }
        }
    }
}