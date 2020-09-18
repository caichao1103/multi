#!/usr/bin/env groovy
pipeline{
    agent any
    stages{
        stage("A"){
            steps{
                script {
                    def fullJobName = env.JOB_NAME
                    def multiBranchJob = fullJobName.substring(0,fullJobName.lastIndexOf('/'))
                    def jobs = jenkinsApiUtils.getEnabledJobs(multiBranchJob)
                    println jobs
                    def multiBranchBuildNumber = 0
                    jobs.each {
                        def job = "${multiBranchJob}/${it}"
                        def jobDetails = jenkinsApiUtils.getJobDetails(job)
                        if (jobDetails.nextBuildNumber != 1) {
                            multiBranchBuildNumber = multiBranchBuildNumber + jobDetails.lastBuild.number
                        }                                                
                    }
                    println multiBranchBuildNumber
                }
            }
        }
    }
}