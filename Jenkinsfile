#!/usr/bin/env groovy
def getTargetEnv() {
    return env.BRANCH_NAME
}
pipeline{
    agent any
    parameters {
        choice(name: 'TARGET_ENV',
            choices: getTargetEnv(),
            description: '测试环境, 线上环境')        
    }
    stages{
        stage("A"){
            steps{
                script {
                    def fullJobName = env.JOB_NAME
                    def multiBranchJob = fullJobName.substring(0,fullJobName.lastIndexOf('/'))
                    def tagViewUrl = jenkinsApiUtls.getJenkinsUrl() + "/${multiBranchJob}/view/tags/api/json"
                    def jobDetails = jenkinsApiUtils.request(tagViewUrl)
                    def enabledJobs = jobDetails.jobs.findAll { it.color != 'disabled' } .collect { it.name }
                    println enablejobs
                    // def jobs = jenkinsApiUtils.getEnabledJobs(multiBranchJob)
                    // println jobs
                    // def multiBranchBuildNumber = 0
                    // jobs.each {
                    //     def job = "${multiBranchJob}/${it}"
                    //     def jobDetails = jenkinsApiUtils.getJobDetails(job)
                    //     if (jobDetails.nextBuildNumber != 1) {
                    //         multiBranchBuildNumber = multiBranchBuildNumber + jobDetails.lastBuild.number
                    //     }                                                
                    // }
                    // println multiBranchBuildNumber
                }
            }
        }
    }
}