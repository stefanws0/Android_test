#!groovy

node {

    stage ('Clone') {
        echo 'now cloning'
        checkout scm
        sh "chmode +x gradlew"

    }

    stage ('Clean') {
        echo 'now cleaning'
        execute("./gradlew clean")

    }

    stage ('Build') {
        echo 'now building'
        execute("./gradlew assemble")

    }

    stage ('Test'){
        echo 'now testing'
        execute("./gradlew connectedCheck")

    }

}