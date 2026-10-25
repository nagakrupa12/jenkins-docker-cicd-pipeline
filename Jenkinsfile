pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Step 1: Packing the toy into the Docker lunchbox...'
                sh 'docker build -t my-web-app:latest .'
            }
        }
        stage('Test') {
            steps {
                echo 'Step 2: Checking if the box is ready...'
                sh 'docker images | grep my-web-app'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Step 3: Running the toy!'
                sh 'docker rm -f my-running-app || true'
                sh 'docker run -d -p 8081:80 --name my-running-app my-web-app:latest'
            }
        }
    }
}
