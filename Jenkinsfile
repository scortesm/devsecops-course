pipeline{
    agent any
    stages{
        stage('build'){
            steps{
                sh 'npm install'
            }
        }
        stage('Deploy-2'){
            steps{
                nodejs (nodeJSInstallationName: 'nodejs'){
                    withAWS (credentials: 'aws-credentials'){
                        sh 'serverless deploy '
                    }
                }
            }
        }
    }
}
