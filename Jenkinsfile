pipeline {
    agent any 
    stages {
        stage('Build') {
            steps {
                sh 'docker login -u="sharad23" -p="Iluvcanada1991"'
                sh 'docker build -t sharad23/hello-flask:v1 .'
                sh 'docker push sharad23/hello-flask:v1'
            }
        }
        stage('Test') {
            agent { docker 'python:3' }
            steps {
                sh 'pip install -r requirements.txt'
                sh 'python test.py'

            }
        }
        stage('Deploy') {
           steps {
                sh 'docker stop my-app'
                sh 'docker rm my-app'
                sh 'docker pull sharad23/hello-flask:v1'
                sh 'docker run -d -p 5000:5000 --name=my-app sharad23/hello-flask:v1'
           } 
        }
    }
}
