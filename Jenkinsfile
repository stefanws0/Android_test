#!groovy

node {

    stage ('Clone') {
        echo 'now cloning'
        checkout scm
        sh "chmod +x gradlew"

    }

    stage ('Clean') {
        echo 'now cleaning'
        sh "./gradlew clean"
    }
    stage ('Build') {
        echo 'now building'
        sh "./gradlew assemble"
    }
    stage ('Test'){
        echo 'now testing'
        sh "./gradlew connectedCheck"

    }
    stage ('getDevices') {
        sh "curl -I http://localhost:3000/api/devices"
    }

}