pipeline {
    agent any

    stages {
        stage('Build in Dev') {
            steps {
                echo "Building application in DEV environment..."
            }
        }

        stage('Approval: Promote to QA') {
            steps {
                script {
                    input message: 'Approve to deploy to QA?', ok: 'Deploy to QA', submitter: 'admin'
                }
            }
        }

        stage('Deploy to QA') {
            steps {
                echo "Deploying to QA environment..."
            }
        }

        stage('Approval: Promote to Prod') {
            steps {
                script {
                    input message: 'Approve to deploy to PROD?', ok: 'Deploy to PROD', submitter: 'admin'
                }
            }
        }

        stage('Deploy to Prod') {
            steps {
                echo "Deploying to PROD environment..."
            }
        }
    }

    post {
        success {
            echo "Pipeline completed successfully ✅"
        }
        failure {
            echo "Pipeline failed ❌"
        }
    }
}
