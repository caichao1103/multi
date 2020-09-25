#!/usr/bin/env groovy
def getRegions() {
    def choices = ['hw', 'cn']
    return choices.join('\n')
}

pipeline{
    agent any
    parameters {
        choice(name: 'BRANCH_NAME',
            choices: getRegions(),
            description: '')
    }
    stages{
        stage("A"){
            steps{
                script {
                    echo "... Done ..."
                }
            }
        }
    }
}