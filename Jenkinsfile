#!/usr/bin/env groovy

def getJobName() {
    return env.JOB_NAME
}

pipeline {
    agent any
    parameters {
        choice(name: 'JOBNAME',
                choices: getJobName(),
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