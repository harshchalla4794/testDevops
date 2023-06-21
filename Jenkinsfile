pipeline {
    agent any
    environment{
        NEW_VERSION='1.3.0'
        SERVER_CREDENTIALS=credentials('server-credentials')
    }
    stages {
        stage('build') {
            steps {
                echo "Hello World Building version ${NEW_VERSION}"
            }
        }
        stage('test') {
            when {
                expression {
                    BRANCH_NAME != 'master'
                }
            }
            steps {
                echo "Hello World Test"
            }
        }
        stage('deploy') {
            steps {
                echo "Hello World Deploy"
                echo "Deploying with ${SERVER_CREDENTIALS}"
            }            
        }
    }
    post {
        always{
            echo "Hello World Always"
        }
        failure{
            echo "Hello World Failure"
        }
        success{
            echo "Hello World Success"
        }        
    }
}
