pipeline {
    agent any
    stages { 
        stage('Build') {
           steps {
                echo 'Starting build'
                sh 'source ~/.bashrc'
                sh "pip install --user -r requirements.txt"

            }
        }
        stage('Test') {
            steps {
                echo 'Starting Testing '
                sh "export PYTHONPATH=src"
                sh "/var/lib/jenkins/.local/bin/pytest tests/"
            }
        }
        stage('Deploy') {
            steps {
                echo 'Starting deployment '
                sh "python src/app.py"
            }
        }
        stage('Release') {
            steps {
                echo 'Starting Release'
            }
        }
    }
}
