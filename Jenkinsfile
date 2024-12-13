pipeline {
    agent any

    stages {
        stage('build') {
            angent{
                docker{
                    image 'node: 18-alpine'
                    reuseNode true
                }
            }
            steps {
                sh '''
                    ls-la
                    node --version
                    npm --version
                    nmp ci
                    npm run build
                    ls -la
                '''
                
            }
        }
    }
}
