pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                 sh 'docker pull node:18-alpine'
                 sh '''
                   ls -la
                   node --version
                   npm --version
                   npm ci
                   npm run build
                   ls -la
                 '''
            }
        }
        stage('Test'){
            steps {
                echo 'test -f build/index.html'
            }
        }
    }
}
