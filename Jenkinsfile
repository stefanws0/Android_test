#!groovy

node {
    stage ('Clone') {
        echo 'now cloning'
        checkout scm
        sh "chmod +x gradlew"
    }
    stage ('Clean') {
        echo 'now cleaning'
        sh "./gradlew --stop"
        sh "./gradlew clean"
    }
    stage ('Build') {
        echo 'now building'
        sh "./gradlew assemble"
    }
    stage ('Test'){
        echo 'now testing'
        sh 'curl -H "Accept: application/json" -H "Content-Type: application/json" http://localhost:3000/api/runtest'
    }
    
}