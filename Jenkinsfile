@Library("belajar-jenkins-shared-library@main") _

import helmipradita.jenkins.Output;

pipeline {
    agent any 
    stages {
        stage("Hello Groovy") {
            steps {
                script {
                    Output.hello("Groovy")
                }
            }
        }
    }
    stages {
        stage("Hello") {
            steps {
                script {
                    hello.world()
                }
            }
        }
    }
}