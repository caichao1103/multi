#!/usr/bin/env groovy
import groovy.json.JsonSlurper

@NonCPS
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
    return json(list.join('\n'))
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

/*
an exception which occurred:
	in field org.jenkinsci.plugins.pipeline.modeldefinition.withscript.WithScriptScript.script
	in object org.jenkinsci.plugins.pipeline.modeldefinition.agent.impl.LabelScript@246e583c
	in field groovy.lang.Closure.delegate
	in object org.jenkinsci.plugins.workflow.cps.CpsClosure2@51c25e74
	in field groovy.lang.Closure.delegate
	in object org.jenkinsci.plugins.workflow.cps.CpsClosure2@7e552b5d
	in field org.jenkinsci.plugins.workflow.cps.CpsThreadGroup.closures
	in object org.jenkinsci.plugins.workflow.cps.CpsThreadGroup@41a07dd8
	in object org.jenkinsci.plugins.workflow.cps.CpsThreadGroup@41a07dd8
Caused: java.io.NotSerializableException: groovy.json.internal.LazyMap
	at org.jboss.marshalling.river.RiverMarshaller.doWriteObject(RiverMarshaller.java:926)
	at org.jboss.marshalling.river.RiverMarshaller.doWriteObject(RiverMarshaller.java:568)
	at org.jboss.marshalling.river.BlockMarshaller.doWriteObject(BlockMarshaller.java:65)
	at org.jboss.marshalling.river.BlockMarshaller.writeObject(BlockMarshaller.java:56)
	at org.jboss.marshalling.MarshallerObjectOutputStream.writeObjectOverride(MarshallerObjectOutputStream.java:50)
	at org.jboss.marshalling.river.RiverObjectOutputStream.writeObjectOverride(RiverObjectOutputStream.java:179)
	at java.io.ObjectOutputStream.writeObject(ObjectOutputStream.java:344)
	at java.util.LinkedHashMap.internalWriteEntries(LinkedHashMap.java:333)
	at java.util.HashMap.writeObject(HashMap.java:1363)
	at sun.reflect.GeneratedMethodAccessor434.invoke(Unknown Source)
	at sun.reflect.DelegatingMethodAccessorImpl.invoke(DelegatingMethodAccessorImpl.java:43)
	at java.lang.reflect.Method.invoke(Method.java:498)
	at org.jboss.marshalling.reflect.JDKSpecific$SerMethods.callWriteObject(JDKSpecific.java:156)
	at org.jboss.marshalling.reflect.SerializableClass.callWriteObject(SerializableClass.java:191)
	at org.jboss.marshalling.river.RiverMarshaller.doWriteSerializableObject(RiverMarshaller.java:1028)
	at org.jboss.marshalling.river.RiverMarshaller.doWriteSerializableObject(RiverMarshaller.java:1019)
	at org.jboss.marshalling.river.RiverMarshaller.doWriteObject(RiverMarshaller.java:920)
	at org.jboss.marshalling.river.BlockMarshaller.doWriteObject(BlockMarshaller.java:65)
	at org.jboss.marshalling.river.BlockMarshaller.writeObject(BlockMarshaller.java:56)
	at org.jboss.marshalling.MarshallerObjectOutputStream.writeObjectOverride(MarshallerObjectOutputStream.java:50)
	at org.jboss.marshalling.river.RiverObjectOutputStream.writeObjectOverride(RiverObjectOutputStream.java:179)
	at java.io.ObjectOutputStream.writeObject(ObjectOutputStream.java:344)
	at com.cloudbees.groovy.cps.SerializableScript.writeObject(SerializableScript.java:26)
	at sun.reflect.GeneratedMethodAccessor512.invoke(Unknown Source)
	at sun.reflect.DelegatingMethodAccessorImpl.invoke(DelegatingMethodAccessorImpl.java:43)
	at java.lang.reflect.Method.invoke(Method.java:498)
	at org.jboss.marshalling.reflect.JDKSpecific$SerMethods.callWriteObject(JDKSpecific.java:156)
	at org.jboss.marshalling.reflect.SerializableClass.callWriteObject(SerializableClass.java:191)
	at org.jboss.marshalling.river.RiverMarshaller.doWriteSerializableObject(RiverMarshaller.java:1028)
	at org.jboss.marshalling.river.RiverMarshaller.doWriteSerializableObject(RiverMarshaller.java:1019)
	at org.jboss.marshalling.river.RiverMarshaller.doWriteSerializableObject(RiverMarshaller.java:1019)
	at org.jboss.marshalling.river.RiverMarshaller.doWriteObject(RiverMarshaller.java:920)
	at org.jboss.marshalling.river.RiverMarshaller.doWriteFields(RiverMarshaller.java:1082)
	at org.jboss.marshalling.river.RiverMarshaller.doWriteSerializableObject(RiverMarshaller.java:1040)
	at org.jboss.marshalling.river.RiverMarshaller.doWriteSerializableObject(RiverMarshaller.java:1019)
	at org.jboss.marshalling.river.RiverMarshaller.doWriteSerializableObject(RiverMarshaller.java:1019)
	at org.jboss.marshalling.river.RiverMarshaller.doWriteObject(RiverMarshaller.java:920)
	at org.jboss.marshalling.river.RiverMarshaller.doWriteFields(RiverMarshaller.java:1082)
	at org.jboss.marshalling.river.RiverMarshaller.doWriteSerializableObject(RiverMarshaller.java:1040)
	at org.jboss.marshalling.river.RiverMarshaller.doWriteSerializableObject(RiverMarshaller.java:1019)
	at org.jboss.marshalling.river.RiverMarshaller.doWriteSerializableObject(RiverMarshaller.java:1019)
	at org.jboss.marshalling.river.RiverMarshaller.doWriteObject(RiverMarshaller.java:920)
	at org.jboss.marshalling.river.RiverMarshaller.doWriteFields(RiverMarshaller.java:1082)
	at org.jboss.marshalling.river.RiverMarshaller.doWriteSerializableObject(RiverMarshaller.java:1040)
	at org.jboss.marshalling.river.RiverMarshaller.doWriteSerializableObject(RiverMarshaller.java:1019)
	at org.jboss.marshalling.river.RiverMarshaller.doWriteSerializableObject(RiverMarshaller.java:1019)
	at org.jboss.marshalling.river.RiverMarshaller.doWriteObject(RiverMarshaller.java:920)
	at org.jboss.marshalling.river.BlockMarshaller.doWriteObject(BlockMarshaller.java:65)
	at org.jboss.marshalling.river.BlockMarshaller.writeObject(BlockMarshaller.java:56)
	at org.jboss.marshalling.MarshallerObjectOutputStream.writeObjectOverride(MarshallerObjectOutputStream.java:50)
	at org.jboss.marshalling.river.RiverObjectOutputStream.writeObjectOverride(RiverObjectOutputStream.java:179)
	at java.io.ObjectOutputStream.writeObject(ObjectOutputStream.java:344)
	at java.util.HashMap.internalWriteEntries(HashMap.java:1793)
	at java.util.HashMap.writeObject(HashMap.java:1363)
	at sun.reflect.GeneratedMethodAccessor434.invoke(Unknown Source)
	at sun.reflect.DelegatingMethodAccessorImpl.invoke(DelegatingMethodAccessorImpl.java:43)
	at java.lang.reflect.Method.invoke(Method.java:498)
	at org.jboss.marshalling.reflect.JDKSpecific$SerMethods.callWriteObject(JDKSpecific.java:156)
	at org.jboss.marshalling.reflect.SerializableClass.callWriteObject(SerializableClass.java:191)
	at org.jboss.marshalling.river.RiverMarshaller.doWriteSerializableObject(RiverMarshaller.java:1028)
	at org.jboss.marshalling.river.RiverMarshaller.doWriteObject(RiverMarshaller.java:920)
	at org.jboss.marshalling.river.RiverMarshaller.doWriteFields(RiverMarshaller.java:1082)
	at org.jboss.marshalling.river.RiverMarshaller.doWriteSerializableObject(RiverMarshaller.java:1040)
	at org.jboss.marshalling.river.RiverMarshaller.doWriteObject(RiverMarshaller.java:920)
	at org.jboss.marshalling.AbstractObjectOutput.writeObject(AbstractObjectOutput.java:58)
	at org.jboss.marshalling.AbstractMarshaller.writeObject(AbstractMarshaller.java:111)
	at org.jenkinsci.plugins.workflow.support.pickles.serialization.RiverWriter.lambda$writeObject$0(RiverWriter.java:144)
	at org.jenkinsci.plugins.scriptsecurity.sandbox.groovy.GroovySandbox.runInSandbox(GroovySandbox.java:237)
	at org.jenkinsci.plugins.workflow.support.pickles.serialization.RiverWriter.writeObject(RiverWriter.java:143)
	at org.jenkinsci.plugins.workflow.cps.CpsThreadGroup.saveProgram(CpsThreadGroup.java:553)
	at org.jenkinsci.plugins.workflow.cps.CpsThreadGroup.saveProgram(CpsThreadGroup.java:530)
	at org.jenkinsci.plugins.workflow.cps.CpsThreadGroup.saveProgramIfPossible(CpsThreadGroup.java:517)
	at org.jenkinsci.plugins.workflow.cps.CpsThreadGroup.run(CpsThreadGroup.java:441)
	at org.jenkinsci.plugins.workflow.cps.CpsThreadGroup.access$400(CpsThreadGroup.java:96)
	at org.jenkinsci.plugins.workflow.cps.CpsThreadGroup$2.call(CpsThreadGroup.java:312)
	at org.jenkinsci.plugins.workflow.cps.CpsThreadGroup$2.call(CpsThreadGroup.java:276)
	at org.jenkinsci.plugins.workflow.cps.CpsVmExecutorService$2.call(CpsVmExecutorService.java:67)
	at java.util.concurrent.FutureTask.run(FutureTask.java:266)
	at hudson.remoting.SingleLaneExecutorService$1.run(SingleLaneExecutorService.java:136)
	at jenkins.util.ContextResettingExecutorService$1.run(ContextResettingExecutorService.java:28)
	at jenkins.security.ImpersonatingExecutorService$1.run(ImpersonatingExecutorService.java:59)
	at java.util.concurrent.Executors$RunnableAdapter.call(Executors.java:511)
	at java.util.concurrent.FutureTask.run(FutureTask.java:266)
	at java.util.concurrent.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1149)
	at java.util.concurrent.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:624)
	at java.lang.Thread.run(Thread.java:748)

http://fcai-u-srv2:8080/job/multibranch-testing/job/branchC/8/console
 */