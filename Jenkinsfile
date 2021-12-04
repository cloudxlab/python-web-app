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
            }
        }
        stage('Deploy') {
            steps {
                echo "Stopping any current running app"
                sh "nohup kill \$(ps -ef | grep /src/app.py | grep -v grep | awk '{print \$2}') &"
                echo 'Starting deployment'
                sh "JENKINS_NODE_COOKIE=dontKillMe nohup python3 src/app.py &"
            }
        }
        stage('Release') {
            steps {
                echo 'Starting Release'
            }
        }
    }
}
