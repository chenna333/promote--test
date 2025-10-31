pipeline {
    agent any

    stages {
        stage('Build in Dev') {
            steps {
                echo "Building application in DEV environment..."
                // Example: sh 'mvn clean package'
            }
        }

        stage('Approval: Promote to QA') {
            steps {
                script {
                    input message: 'Approve to deploy to QA?', ok: 'Deploy to QA'
                }
            }
        }

        stage('Deploy to QA') {
            steps {
                echo "Deploying to QA environment..."
                // Example: sh './deploy_qa.sh'
            }
        }

        stage('Approval: Promote to Prod') {
            steps {
                script {
                    input message: 'Approve to deploy to PROD?', ok: 'Deploy to PROD'
                }
            }
        }

        stage('Deploy to Prod') {
            steps {
                echo "Deploying to PROD environment..."
                // Example: sh './deploy_prod.sh'
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
