pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build') {
            steps {
                echo 'No build needed for static HTML.'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploy your static site here (e.g., Vercel CLI commands).'
            }
        }
    }
}
