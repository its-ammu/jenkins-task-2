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
                // docker build -t its-ammu/php .
                // cd mysql
                // docker build -t its-ammu/mysql .
                // '''
                
            }
        }
        stage('Deploy'){
            steps{
                echo "Deploying..."
                
                sh """
                docker run --network=host -e MYSQL_PASSWORD=pass -e MYSQL_USER=intern -e MYSQL_ROOT_PASSWORD=pass -e MYSQL_DATABASE=todo its-ammu/mysql
                """
                
            }
        }
    }
}
