pipeline {
    agent any
    stages { 
        stage('Build') {
           steps {
                echo 'Starting build'
                sh "sudo yum -y install python3"
                sh "sudo pip3 install --upgrade pip"
                sh "python3 -m venv venv"
                sh "source venv/bin/activate"
                sh "pip3 install -r requirements.txt"

            }
        }
        stage('Test') {
            steps {
                echo 'Starting Testing'
                sh ". ~/.bashrc"
                sh "echo $PATH"
                sh "which pytest"
                sh "pytest"
            }
        }
        stage('Deploy') {
            steps {
                echo 'Starting deployment'
                sh "BUILD_ID=pywebapp nohup python3 src/app.py &"
            }
        }
        stage('Release') {
            steps {
                echo 'Starting Release'
            }
        }
    }
}
