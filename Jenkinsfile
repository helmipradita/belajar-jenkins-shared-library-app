pipeline {
    // agent any
    // agent {
    //     node {
    //         label 'linux && java17'
    //     }
    // }
    agent none

    environment {
        AUTHOR = "Helmi Pradita"
        EMAIL = "helmipraditaa@gmail.com"
    }

    options {
        disableConcurrentBuilds()
        timeout(time: 10, unit: 'MINUTES')
    }

    stages {
        stage ("Prepare") {
            environment {
                APP = credentials('root-vps_jenkins-agent')
            }
            agent {
                node {
                    label "linux && java17"
                }
            }
            steps {
                echo("Author: ${AUTHOR}")
                echo("Email: ${EMAIL}")
                echo("SSH User: ${APP_USR}")
                echo("SSH Pass: ${APP_PSW}")
                sh('echo "App Pass: $APP_PSW" >> "rahasia.txt"')
                echo("Start Job : ${env.JOB_NAME}")
                echo("Start Build : ${env.BUILD_NUMBER}")
                echo("Branch Name : ${env.BRANCH_NAME}")
                echo("Finish Prepare ")
            }
        }
        stage('Build') {
            agent {
                node {
                    label "linux && java17"
                }
            }
            steps {
                script {
                    def data = [
                        "name": 'helmi',
                        "email": 'helmi@gmail.com'
                    ]
                    writeJSON(file: 'data.json', json: data)
                }


                
                echo('Start Build ')
                sh('./mvnw clean compile test-compile')
                echo('Finish Build ')
            }
        }
        stage('Test') {
            agent {
                node {
                    label "linux && java17"
                }
            }
            steps {
                echo('Start Test ')
                sh('./mvnw clean compile test-compile')
                echo('Finish Test ')
            }
        }
        stage('Deploy') {
            agent {
                node {
                    label "linux && java17"
                }
            }
            steps {
                echo('Hello Deploy 1')
                sleep(5)
                echo('Hello Deploy 2')
                echo('Hello Deploy 3')
            }
        }
        
    }
    post {
        always {
            echo 'This will always run'
        }
        success {
            echo 'This will run only if successful'
        }
        failure {
            echo 'This will run only if failed'
        }
        unstable {
            echo 'This will run only if the run was marked as unstable'
        }
        changed {
            echo 'This will run only if the state of the Pipeline has changed'
            echo 'For example, if the Pipeline was previously failing but is now successful'
        }
        cleanup {
            echo 'Do some cleanup here'
        }

    }   
}