pipeline {
    agent any
    stages { 
        stage('Build') {
           steps {
                echo 'Starting build'
                python3 -m venv venv
                source venv/bin/activate
                pip install -r requirements.txt
            }
        }
        stage('Test') {
            steps {
                echo 'Starting Testing '
                export PYTHONPATH=src
                pytest
            }
        }
        stage('Deploy') {
            steps {
                echo 'Starting deployment '
                python3 src/app.py &
            }
        }
        stage('Release') {
            steps {
                echo 'Starting Release'
            }
        }
    }
}
