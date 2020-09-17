#!/usr/bin/env groovy
pipeline{
    agent any
    stages{
        stage("A"){
            steps{
                script {
                    def fullJobName = env.JOB_NAME
                    multiBranchJob = fullJobName.subString(0,fullJobName.lastIndexOf('/'))
                    jobs = jenkinsApiUtils.getEnabledJobs(job)
                    println jobs
                }
            }
        }
    }
}