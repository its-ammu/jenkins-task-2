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
                
                sh """
                docker run --network=host -e MYSQL_PASSWORD=$SECRET_PASS -e MYSQL_USER=intern -e MYSQL_ROOT_PASSWORD=$SECRET_PASS its-ammu/mysql
                """
                
            }
        }
    }
}
