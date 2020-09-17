#!/usr/bin/env groovy
pipeline{
    agent any
    stages{
        stage("A"){
            steps{
                script {
                    def fullJobName = env.JOB_NAME
                    def multiBranchJob = fullJobName.substring(0,fullJobName.lastIndexOf('/'))
                    def jobs = jenkinsApiUtils.getEnabledJobs(job)
                    println jobs
                }
            }
        }
    }
}