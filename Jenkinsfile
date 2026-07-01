pipeline {
    agent any

    stages {

        stage('Build') {
            steps {
                sh 'python3 -m venv venv'
                sh 'venv/bin/pip install -r requirements.txt'
            }
        }

        stage('Test') {
            steps {
                sh 'venv/bin/pytest'
            }
        }

        stage('Deploy') {
    steps {
        sh '''
            rm -rf /tmp/flask-staging
            mkdir -p /tmp/flask-staging
            cp -r * /tmp/flask-staging/
        '''
        echo 'Application deployed to staging successfully.'
    }
}
    }
}