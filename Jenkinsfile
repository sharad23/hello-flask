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
    }
}
