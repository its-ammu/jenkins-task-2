pipeline {
	agent any
    stages{
        stage('Build'){
            steps{
                echo "Building..."
                docker.build("sample:${env.BUILD_ID}")
            }
        }
        stage('Deploy'){
            steps{
                echo "Deploying..."
            }
        }
    }
}
