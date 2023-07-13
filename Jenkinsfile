pipeline {
    agent { 
        node {
            label 'docker-agent-python'
            }
      }
  triggers {
    pollSCM '*/6 * * * *'
  }
    stages {
        stage('Build') {
            steps {
                echo "Building.."
                sh '''
                cd petersapp
                pip install -r requirements.txt
                '''
            }
        }
        stage('Test') {
            steps {
                echo "Testing.."
                sh '''
                cd petersapp
                python3 hello.py
                python3 hello.py --name=Phil
                '''
            }
        }
        stage('Deliver') {
            steps {
                echo 'Deliver....'
                sh '''
                echo "doing delivery stuff.."
                '''
            }
        }
    }
}
