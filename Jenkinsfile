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
        stage('HTML Linting') {
            steps {
                sh 'tidy -q -e *.html'
            }
        }
        stage('Upload to S3') {
            steps {
                withAWS(region:'us-west-2') {
                    s3Upload(file:'index.html', bucket:'udacity-test-bassel', path:'index.html')
                }
            }
        }

    }
}