pipeline {
	agent any
    stages{
        stage('Build'){
            steps{
                echo "Building..."
                def testImage = docker.build("sample:${env.BUILD_ID}")
            }
        }
        stage('Deploy'){
            steps{
                echo "Deploying..."
            }
        }
    }
}
