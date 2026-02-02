pipeline {
	agent none 
	triggers {
		githubPush()
	}
	stages {
		stage('pushing to test') {
			agent {label 'test'}
			steps {
				git branch : 'develop' , url : 'https://github.com/p-shashidhar-gowda/Jenkins-practice.git'
				sh 'mkdir -p ~/test-app'
				sh 'cp -r * ~/test-app'
			}
		}
		stage('pushing to prod') {
			agent {label 'prod'}
			steps {
				git branch : 'develop' , url : 'https://github.com/p-shashidhar-gowda/Jenkins-practice.git'
				sh 'mkdir -p ~/prod-app'
				sh 'cp -r * ~/prod-app'
			}
		}
	}
}