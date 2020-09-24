#!/usr/bin/env groovy

def getBranchName() {
    return env.BRANCH_NAME
}

pipeline {
    agent any
    parameters {
        choice(name: 'BranchName',
                choices: getBranchName(),
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