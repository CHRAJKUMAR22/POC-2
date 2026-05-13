pipeline {
    agent any

    stages {

        stage('Clone') {
            steps {
                git branch: 'main', url: 'https://github.com/CHRAJKUMAR22/POC-2.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t myapp:v1 .'
            }
        }

        stage('Deploy Container') {
            steps {
                sh 'docker rm -f myapp || true'
                sh 'docker run -d -p 80:80 --name myapp myapp:v1'
            }
        }
    }
}
