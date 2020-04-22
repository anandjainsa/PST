@Library('pstsharedlibrary')_

pipeline {

    agent any
//    agent {
//        label "nodename"
//    }
    tools {
        jdk "java1.8"
        maven  "maven3"
    }

//    environment {
//
//        project_name = "crewpro"
//        port = "8090"
//        env = "Dev"
//        hostname =""
//    }
    options {
        // Only keep the 10 most recent builds
        buildDiscarder(logRotator(numToKeepStr:'2'))
    }
    stages {
        stage ('Build') {
            steps {
                // build
                mavenBuild();
            }
    }

    }
    post {
        always {
            sendNotifications currentBuild.result
        }
    }
}
