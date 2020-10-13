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
                    def totalBuildNumber = 0
                    def jobs = jenkinsApiUtils.getJobDetails(multiBranchJob).jobs
                    jobs.each { job ->
                        println job
                        jobDetails = jenkinsApiUtils.request(job.url)
                        println jobDetails.lastBuild.getClass()
                        if (! jobDetails.lastBuild.equals(null) ) {
                            println jobDetails.lastBuild.number
                            totalBuildNumber = totalBuildNumber + jobDetails.lastBuild.number
                        }
                    }
                    println "totalBuildNumber is: $totalBuildNumber"
                }
			}
		}
    }
}