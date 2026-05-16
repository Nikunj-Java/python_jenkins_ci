pipeline {
    agent any

    stages {

        stage('Clone Repository') {
            steps {
                git branch: 'main',
                url: 'https://github.com/Nikunj-Java/python_jenkins_ci.git'
            }
        }

        stage('Check Python Version') {
            steps {
                sh 'python3 --version'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'pip3 install -r requirements.txt'
            }
        }

        stage('Run Test Cases') {
            steps {
                sh 'pytest'
            }
        }
    }

    post {
        success {
            echo 'Calculator CI Pipeline Successful!'
        }

        failure {
            echo 'Pipeline Failed!'
        }
    }
}