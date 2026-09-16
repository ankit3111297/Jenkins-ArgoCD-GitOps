pipeline {
	agent any
	tools {
		nodejs 'NodeJS'
	}
	environment {
		DOCKER_HUB_REPO = 'ankitankur/my-k8s-app'
	}
	stages {
		stage('Checkout Github'){
			steps {
		    git branch: 'main', credentialsId: 'GitOps-token-GitHub', url: 'https://github.com/ankit3111297/Jenkins-ArgoCD-GitOps.git'
			}
		}		
		stage('Install node dependencies'){
			steps {
				sh 'npm install'
			}
		}
		stage('Build Docker Image'){
			steps {
				script {
					echo 'building docker image...'
					docker.build("${DOCKER_HUB_REPO}:latest")
					
				}
			}
		}
		stage('Trivy Scan'){
			steps {
				echo "trivy"
			}
		}
		stage('Push Image to DockerHub'){
			steps {
				script {
					echo 'pushing docker image to DockerHub...'
					
						}
					}
				}
			
		stage('Install Kubectl & ArgoCD CLI'){
			steps {
				
				echo 'installing Kubectl & ArgoCD cli...'
				
			}
		}
		stage('Apply Kubernetes Manifests & Sync App with ArgoCD'){
			steps {
				script {
					echo "just"
						
					}	
				}
			}
		}
	

	post {
		success {
			echo 'Build & Deploy completed succesfully!'
		}
		failure {
			echo 'Build & Deploy failed. Check logs.'
		}
	}
}
