@Library("belajar-jenkins-shared-library@main") _

import helmipradita.jenkins.Output;

pipeline {
    agent any 
    stages {
        stage("Global Variable") {
            steps {
                script {
                    echo(author.name())
                    echo(author.channel())
                }
            }
        }

        stage("Hello Groovy") {
            steps {
                script {
                    Output.hello(this, "Groovy")
                }
            }
        }

        stage("Hello") {
            steps {
                script {
                    hello.world()
                }
            }
        }
    }
}