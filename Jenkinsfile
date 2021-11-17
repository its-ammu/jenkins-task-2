pipeline {
	agent any
    stages{
        stage('Build'){
            steps{
                echo "Building..."
                sh '''
                docker build -t its-ammu/php .
                cd mysql
                docker build -t its-ammu/mysql .
                '''
                
            }
        }
        stage('Deploy'){
            steps{
                echo "Deploying..."
                withCredentials([string(credentialsId: 'mysql password', variable: 'MYSQL_PASS')]) {
                    echo $MYSQL_PASS
                }
            }
        }
    }
}
