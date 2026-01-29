pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                git 'https://github.com/USERNAME/hello-devops.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'pip3 install -r requirements.txt'
            }
        }

        stage('Run Tests') {
            steps {
                sh 'pytest'
            }
        }

        stage('Build Package') {
            steps {
                sh 'zip -r hello-devops.zip .'
            }
        }

        stage('Archive Artifacts') {
            steps {
                archiveArtifacts artifacts: 'hello-devops.zip'
            }
        }
    }
}
