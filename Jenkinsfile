pipeline {
    agent any

    environment {
        DIRECTORY_PATH = "main.py"
        TESTING_ENVIRONMENT = "Yash's Test"
        PRODUCTION_ENVIRONMENT = "Yash's Prod"
    }

    stages {
        stage('Build') {
            steps {
                echo "Building is in progress"
                echo "Buidl done!!!"
            }
        }

        stage('Test') {
            steps {
                echo "Running unit tests"
                echo "Testing is Done!!!"
            }
        }

        stage('Code Quality Check') {
            steps {
                echo "Checking the quality of the code"
            }
        }

        stage('Deploy') {
            steps {
                echo "Deployment is done"
            }
        }

        stage('Approval') {
            steps {
                echo "Waiting for manual approval..."
                sleep time: 10, unit: 'SECONDS'
            }
        }

        stage('Deploy to Production') {
            steps {
                echo "Deploying the code to the production: (${env.PRODUCTION_ENVIRONMENT})"
            }
        }

        post {
        success {
            echo "Pipeline executed successfully!"
            emailext body: 'Pipeline execution successful.', subject: 'Pipeline Success', to: 'yashmaheta251@gmail.com'
        }
        failure {
            echo "Pipeline execution failed!"
            emailext body: 'Pipeline execution failed.', subject: 'Pipeline Failure', to: 'yashmaheta251@mail.com'
        }
    }
    }
}
