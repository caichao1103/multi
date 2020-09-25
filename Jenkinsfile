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



pipeline {
    agent any
    parameters {
        choice(name: 'APP_NAME',
                choices: getAppNames(),
                description: '')
    }
    stages {
        stage("A") {
            steps {
                script {
                    echo "...."
                }
            }
        }
    }
}