pipeline {
    // agent any
    agent {
        node {
            label 'linux && java17'
        }
    }
    stages {
        stage('Build') {
            steps {
                script {
                    for(int i = 0; i < 10; i++) {
                        echo "Hello ${i}"
                    }
                }
                echo('Start Build ')
                sh('./mvnw clean compile test-compile')
                echo('Finish Build ')
            }
        }
        stage('Test') {
            steps {
                 echo('Start Test ')
                sh('./mvnw clean compile test-compile')
                echo('Finish Test ')
            }
        }
        stage('Deploy') {
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