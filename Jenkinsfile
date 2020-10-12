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

    stages{
		stage('build number') {
			steps {
				script {
                    def fullJobName = env.JOB_NAME
                    def multiBranchJob = fullJobName.substring(0,fullJobName.lastIndexOf('/'))
                    def jobs = jenkinsApiUtils.getJobDetails(multiBranchJob).jobs
                    printf jobs

                }
			}
		}
    }
}