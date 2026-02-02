pipeline{
	agent none 

	triggers{
		githubPush()
	}

	stages{

		stage('get code') {
			agent any 
			steps {
				git branch: 'develop'
				url: https://github.com/p-shashidhar-gowda/Jenkins-practice.git
			}
		}

		stage('deploy to test'){
			agent {label 'test'}
			steps {
				sh 'mkdir -p ~/test-app'
				sh 'cp -r * ~/test-app'
			}
		}

		stage('deploy to prod') {
			agent {label 'prod'}
			steps {
				sh 'mkdir -p ~/prod-app'
				sh 'cp -r * ~/prod-app'
			}
		}
	}
}