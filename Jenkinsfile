pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/Jeevanantham74/python-mail.git'
            }
        }

        stage('Build') {
            steps {
                bat '"C:\\Users\\Admin\\AppData\\Local\\Programs\\Python\\Python313\\python.exe" --version'
                bat '"C:\\Users\\Admin\\AppData\\Local\\Programs\\Python\\Python313\\python.exe" -m py_compile app.py'

                echo 'Build successful: app.py compiled with no syntax errors'
            }
        }

        stage('Send Notification') {
            steps {
                echo "EMAIL WOULD BE SENT -> To: student@example.com | Subject: Build Notification: ${env.JOB_NAME} #${env.BUILD_NUMBER}"
            }
        }
    }
}