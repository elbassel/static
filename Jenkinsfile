pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'echo hello world'
                sh '''
                    echo "Multiline shellworks too"
                    ls -lah
                '''
            }
        }
        stage('Deploy') {
            steps {
                withAWS(region:'eu-west-1') {
                    s3Upload(file:'index.html', bucket:'udacity-test-bassel', path:'index.html')
                }
            }
        }

    }
}