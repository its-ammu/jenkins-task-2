pipeline {
	agent any
    stages{
        stage('Build'){
            steps{
                echo "Building..."
                script{
                    sudo docker.build("sample:latest")
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
