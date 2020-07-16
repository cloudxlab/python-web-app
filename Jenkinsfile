pipeline {
    agent any
    stages { 
        stage('Build') {
           steps {
                echo 'Starting build'
                sh "python3 -m venv"
                sh "source venv/bin/activate"
                sh "pip3 install -r requirements.txt"
            }
        }
        stage('Test') {
            steps {
                echo 'Starting Testing '
                export PYTHONPATH=src
                sh "pytest"
            }
        }
        stage('Deploy') {
            steps {
                echo 'Starting deployment '
                sh "python3 src/app.py &"
            }
        }
        stage('Release') {
            steps {
                echo 'Starting Release'
            }
        }
    }
}
