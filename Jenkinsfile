@Library("belajar-jenkins-shared-library@main") _

import helmipradita.jenkins.Output;

pipeline {
    agent any 
    stages {
        stage("Hello Person") {
            steps {
                script {
                    hello.person([
                        firstName: "Helmi",
                        lastName: "Pradita",
                    ])
                }
            }
        }

        stage("Maven Build") {
            steps {
                script {
                    maven(["clean", "compile", "test"])
                }
            }
        }

        stage("Global Variable") {
            steps {
                script {
                    echo(author())
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