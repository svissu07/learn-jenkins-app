pipeline {
    agent any

    stages {
        stage('Build') {
             agent {
                docker {
                    image 'node:18-alpine'
                    reuseNode true
                }
            }
            steps {
                echo 'Hello World from build stage'
            }
        }
        stage('Test') {
            steps {
                echo 'Hello World from Test'
                sh 'test -f build/index.html'
                sh 'npm test'
            }
        }
    }
}