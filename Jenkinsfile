pipeline {
	agent any
    stages{
        stage('Build'){
            steps{
                echo "Building..."
                docker.build sample
            }
        }
        stage('Deploy'){
            steps{
                echo "Deploying..."
            }
        }
    }
}
