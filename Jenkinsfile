pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Building the code...'
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                echo 'Running unit and integration tests...'
            }
            post {
                success {
                    echo 'Unit and integration tests passed.'
                    emailext attachLog: true, 
                             body: 'Tests passed successfully.',
                             subject: 'Test Success',
                             to: 'yashmaheta251@gmail.com'
                }
                failure {
                    echo 'Unit and integration tests failed.'
                    emailext attachLog: true, 
                             body: 'Tests failed. Please check the logs for details.',
                             subject: 'Test Failure',
                             to: 'yashmaheta251@gmail.com'
                }
            }
        }
        stage('Code Analysis') {
            steps {
                echo 'Performing code analysis...'
                echo 'Tool: SonarQube'
            }
        }
        stage('Security Scan') {
            steps {
                echo 'Performing security scan...'
            }
            post {
                success {
                    echo 'Security scan passed.'
                    emailext attachLog: true, 
                             body: 'Security scan passed successfully.',
                             subject: 'Security Scan Success',
                             to: 'yashmaheta251@gmail.com'
                }
                failure {
                    echo 'Security scan failed.'
                    emailext attachLog: true, 
                             body: 'Security scan failed. Please check the logs for details.',
                             subject: 'Security Scan Failure',
                             to: 'yashmaheta251@gmail.com'
                }
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo 'Deploying to staging environment...'
                echo 'Staging server: AWS EC2'
            }
        }
        stage('Deploy to Production') {
            steps {
                echo 'Deploying to production environment...'
                echo 'This message is set to check whether the build triggers dynamically or not'
            }
        }
    }
}