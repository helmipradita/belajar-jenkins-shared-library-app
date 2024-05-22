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
                echo('Hello Build 1')
                echo('Hello Build 2')
                echo('Hello Build 3')
            }
        }
        stage('Test') {
            steps {
                echo('Hello Test 1')
                echo('Hello Test 2')
                echo('Hello Test 3')
            }
        }
        stage('Deploy') {
            steps {
                echo('Hello Deploy 1')
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