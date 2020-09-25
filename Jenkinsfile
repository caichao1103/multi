#!/usr/bin/env groovy
def getBranchName() {
    return env.BRANCH_NAME
}
def getDockerRegistry() {
    return dockerBuild.getDockerRegistry()
}
pipeline{
    agent any
    parameters {
        choice(name: 'BRANCH_NAME',
            choices: getBranchName(),
            description: '')
        choice(name: 'Docker_REGISTRY',
            choices: getDockerRegistry(),
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