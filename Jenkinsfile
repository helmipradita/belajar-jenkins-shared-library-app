pipeline {
    // agent any
    // agent {
    //     node {
    //         label 'linux && java17'
    //     }
    // }
    agent none

    stages {
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