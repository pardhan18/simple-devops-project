pipeline {

    agent any

    stages {

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t demo-site .'
            }
        }

        stage('Stop Old Container') {
            steps {
                sh 'docker stop demo-container || true'
                sh 'docker rm demo-container || true'
            }
        }

        stage('Run New Container') {
            steps {
                sh 'docker run -d --name demo-container -p 80:80 demo-site'
            }
        }

    }

}
