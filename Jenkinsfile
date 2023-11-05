pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                sh 'rm -Rf jenkins'
                sh 'git clone https://github.com/SUSIGUGH/jenkins.git'
                sh 'cd jenkins && ls -ltr'
                sh 'sudo docker ps'
                sh 'sudo docker images'
                sh 'sudo docker build -t susigughnginx01 .'
                sh 'sudo docker images'
                sh 'sudo docker stop susigughnginx01'
                sh 'sudo docker rm susigughnginx01'
                sh 'sudo docker run -dit --name susigughnginx01 -p8020:80 susigughnginx01'
            }
        }
    }
}
