pipeline {
    agent any

    environment {
        SLACK_WEBHOOK = credentials('slack-webhook')  // Your stored Slack webhook ID
    }

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/TSolutions3A/moonsky.git' // Replace with your repo URL
            }
        }

        stage('Build') {
            steps {
                echo 'Building the project (no build needed for static HTML)'
                // If you want, add validation commands here
            }
        }

        stage('Deploy') {
            steps {
                echo 'Simulating deployment (add your deploy steps here)'
                // e.g. copy files to web server or deploy to Vercel
            }
        }
    }

    post {
        success {
            slackSend (
                webhookUrl: SLACK_WEBHOOK,
                color: 'good',
                message: "✅ Build Success: ${env.JOB_NAME} #${env.BUILD_NUMBER}"
            )
        }
        failure {
            slackSend (
                webhookUrl: SLACK_WEBHOOK,
                color: 'danger',
                message: "❌ Build Failed: ${env.JOB_NAME} #${env.BUILD_NUMBER}"
            )
        }
    }
}
