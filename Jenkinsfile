pipeline {
	agent any
    stages{
        stage('Build'){
            steps{
                echo "Building..."
                script{
                    docker.build("sample:latest")
                }
                
            }
        }
        stage('Deploy'){
            steps{
                echo "Deploying..."
            }
        }
    }
}
