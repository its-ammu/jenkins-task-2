pipeline {
	agent any
    environment {
        SECRET_PASS = credentials('mysql password')
    }
    stages{
        stage('Build'){
            steps{
                echo "Building..."
                // sh '''
                // sudo docker build -t its-ammu/php .
                // cd mysql
                // sudo docker build -t its-ammu/mysql .
                // '''
                
            }
        }
        stage('Deploy'){
            steps{
                echo "Deploying..."
                echo SECRET_PASS
                
            }
        }
    }
}
