pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                echo 'Hello SuSiGuGh'
                sh 'pwd'
                sh 'ls -ltr'
                sh 'touch a.txt'
                sh 'ls -ltr'
                sh 'rm -Rf jenkins'
                sh 'git clone https://github.com/SUSIGUGH/jenkins.git'
                sh 'cd jenkins && ls -ltr'
                sh 'ls -ltr'
            }
        }
    }
}
