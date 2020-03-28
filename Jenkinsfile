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
    }
}