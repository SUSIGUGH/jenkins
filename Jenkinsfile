pipeline
{
  agent any

    stages {

        stage('Git Connect') {
            steps {
                sh 'rm -Rf jenkins'
                sh 'git clone https://github.com/SUSIGUGH/jenkins.git'
                sh 'cd jenkins && ls -ltr'
		}
		}


	stage('Docker Image Creation')
	{
	steps{
                sh 'sudo docker ps'
                sh 'sudo docker images'
                sh 'sudo docker build -t susigughnginx01 .'
                sh 'sudo docker images'
                sh 'sudo docker stop susigughnginx01'
                sh 'sudo docker rm susigughnginx01'
                sh 'sudo docker run -dit --name susigughnginx01 -p8020:80 susigughnginx01'
		}
		}


	stage('Tag Image')
	{
	steps{
	       sh 'sudo docker image tag susigughnginx01 susigugh/susigughnginx01:1.0'
            }
        }


	stage('Push Image to Docker Hub')
	{
	steps{
        sh 'sudo docker login -u=${udockersusigugh} -p=${pdockersusigugh} && sudo docker push susigugh/susigughnginx01:1.0'
	}
	}

	stage('AWS Setup')
	{
	steps
	{
	sh 'terraform init'
	sh 'terraform apply -auto-approve'
	sh 'terraform destory -auto-approve'
	}
	}

  }
}
