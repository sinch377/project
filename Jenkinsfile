pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                git 'https://github.com/sinch377/project.git'
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
                sh 'zip -r project.zip .'
            }
        }

        stage('Archive Artifacts') {
            steps {
                archiveArtifacts artifacts: 'project.zip'
            }
        }
    }
}
