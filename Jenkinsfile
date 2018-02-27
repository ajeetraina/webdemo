pipeline {
    agent {
        docker { image 'ruby:2.2' }
    }
    stages {
        stage('Test') {
            steps {
                sh 'ruby version'
            }
        }
    }
}
