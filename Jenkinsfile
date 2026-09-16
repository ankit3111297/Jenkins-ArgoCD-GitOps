pipeline {
	agent any
	
	stages {
		stage('Checkout Github'){
			steps {
			git branch: 'main', credentialsId: 'GitOps-token-GitHub', url: 'https://github.com/ankit3111297/Jenkins-ArgoCD-GitOps.git'
			}
		}		
		stage('Install node dependencies'){
			steps {
				echo "node"
			}
		}
		stage('Build Docker Image'){
			steps {
				script {
					echo 'building docker image...'
					
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
