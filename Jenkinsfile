pipeline {
    agent any

    stages {
        stage('Build') {
            agent{
                docker{
                    image 'node:18-alpine'
                    reuseNode true
                }
            }
            steps {
                echo 'Hello World'
                sh'''
                ls -la
                node --version
                npm --version
                npm ci
                npm run Build
                ls -la
                '''
                
            }
        }
        stage('test'){
            agent{
            docker{
                    image 'node: 18-alpine'
                    reuseNode true
                }
            }
            steps{
                sh'''
                    Test -f build/index.htlm
                    npm test
                '''
            }

        }
    }
}
