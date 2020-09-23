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
                    def tagViewUrl = jenkinsApiUtils.getJobUrl(multiBranchJob) + "/view/tags"
                    def tags = []
                    try {
                        def jobDetails = jenkinsApiUtils.request(tagViewUrl)
                        println jobDetails.jobs 
                        tags = jobDetails.jobs.collect { it.name }
                    }
                    catch (ex) {
                        echo "there is not any tag for the git repository" 
                    }

                    println tags

                    println tags[0]
                    println tags.contains(env.BRANCH_NAME)
                    println "env.TAG_NAME is " + env.TAG_NAME

                    if (env.TAG_NAME) {
                        println "this is a tag"
                    }                        
                    else {
                        println "this is NOT a tag"
                    }
                        

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