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

        stage('E2E'){
            steps {
                sh '''
                   docker pull mcr.microsoft.com/playwright:v1.39.0-jammy
                   npm install -g serve
                   serve -s build
                   npx playwrihgt test
                '''
            }
        }
    }
}
