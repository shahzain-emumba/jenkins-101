pipeline {
    agent { 
        node {
            label 'python-agent'
            }
      }
    triggers {
        pollSCM '* * * * *'
    }
    stages {
        stage('Build') {
            steps {
                echo "Building.."
                sh '''
                cd myapp
                pip install -r requirements.txt
                '''
            }
        }
        stage('Test') {
            steps {
                echo "Testing.."
                sh '''
                cd myapp
                python3 hello.py
                python3 hello.py --name=Zain
                '''
            }
        }
        stage('Deliver') {
            steps {
                echo 'Deliver....NEW'
                sh '''
                echo "doing delivery stuff NEW.."
                '''
            }
        }
    }
}