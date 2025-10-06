pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/NahidCSERU/jenkins-nodejs-docker-demo.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t jenkins-nodejs-docker-demo:latest .'
            }
        }

        stage('Run Container') {
            steps {
                script {
                    def containerExists = sh(script: "docker ps -a --format '{{.Names}}' | grep -w nodejs-demo || true", returnStdout: true).trim()
                    if (containerExists) {
                        sh "docker rm -f nodejs-demo"
                    }
                    sh 'docker run -d -p 3000:3000 --name nodejs-demo jenkins-nodejs-docker-demo:latest'
                }
            }
        }

        stage('Verify') {
            steps {
                sh 'docker ps | grep nodejs-demo'
            }
        }
    }

    post {
        always {
            echo 'Cleaning up...'
        }
    }
}
