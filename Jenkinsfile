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
                withAWS(region:'us-west-2') {
                    s3Upload(file:'index.html', bucket:'udacity-test-bassel', path:'index.html', acl: 'PublicRead')
                }
            }
        }

    }
}