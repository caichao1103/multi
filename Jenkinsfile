#!/usr/bin/env groovy
import groovy.json.JsonSlurper


def getAppNames() {
    def url = 'https://test-api.kingsoftgame.com/v2/uout/app/getAppInfoList'
    def http = new URL(url).openConnection() as HttpURLConnection
    http.setRequestMethod('GET')
    http.setRequestProperty("Accept", 'application/json')
    http.setRequestProperty("Content-Type", 'application/json')
    response = new JsonSlurper().parseText(http.inputStream.getText('UTF-8'))
    def list = []
    response.each {
        list.add(it.appName)
    }
    return list
}

//def appName_script = '''
//    def appNameList = getAppNames()
//    return appNameList
//'''


properties([
        parameters([
                [$class: 'ChoiceParameter', choiceType: 'PT_SINGLE_SELECT',   name: 'APP_NAME',
                 script: [$class: 'GroovyScript', fallbackScript: [classpath: [], sandbox: true, script: 'return ["ERROR"]'],
                 script: [classpath: [], sandbox: true, script: "return getAppNames()"]]]
        ])
])

pipeline {
    agent any

    stages {
        stage("Choice") {
            steps {
                script {
                    echo "...."
                }
            }
        }
    }
}