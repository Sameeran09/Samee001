ipipeline {
    agent any
    environment{
        DOCKERHUB_CREDS = credentials('dockerhub')
    }
    stages {
        stage('Clone Repo') {
            steps {
                checkout scm
             echo 'ls *'
            }
        }
        stage('Build Image') {
            steps {
		echo 'docker build -t Vanshu009/jenkinstest:$BUILD_NUMBER ./docker build -f jenkinstest0 ./'
            }
        }
        stage('Docker Login') {
            steps {
                echo 'echo $DOCKERHUB_CREDS_PSW | docker login -u $DOCKERHUB_CREDS_USR --password-stdin'                
                }
            }
        stage('Docker Push') {
            steps {
                echo 'docker push Vanshu009/jenkinstest:$BUILD_NUMBER'
                }
            }
        }
    post {
		always {
			echo 'docker logout'
		}
	 }
    }

