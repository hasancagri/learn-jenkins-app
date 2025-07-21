pipeline {
    agent any

    stages {
        stage('Build') {
            //This is a comment
            /*
            Line 1
            Line 2
            */
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
                sh '''
                   #test -f build/index.html
                   npm test 
                '''
            }
        }
    }
    post {
        always {
            junit 'test-results/junit.xml'
        }
    }
}
