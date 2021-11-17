pipeline {
    agent any
    environment {
        SECRET_PASS = credentials('mysql password')
    }
    stages{
        stage('Build'){
            steps{
                echo "Building..."
                sh '''
                docker build -t intern/php .
                cd mysql
                docker build -t intern/mysql .
                '''
            }
        }
        stage('Deploy'){
            steps{
                
                echo "Removing last build..."
                sh """
                SUCCESS_BUILD=`wget -qO- http://<jenkins_url>:8080/job/jobname/lastSuccessfulBuild/buildNumber`
                docker rm -f "${SUCCESS_BUILD}mysql" && echo "container ${SUCCESS_BUILD}mysql removed" || echo "container ${SUCCESS_BUILD}mysql does not exist"
                docker rm -f "${SUCCESS_BUILD}php" && echo "container ${SUCCESS_BUILD}php removed" || echo "container ${SUCCESS_BUILD}php does not exist"
                """

                echo "Deploying new build..."
                sh """
                docker run -d --network=host -e MYSQL_PASSWORD=${SECRET_PASS} -e MYSQL_USER=intern -e MYSQL_ROOT_PASSWORD=${SECRET_PASS} -e MYSQL_DATABASE=todo --name "${BUILD_ID}mysql" intern/mysql
                docker run -d -p 80:5000 -e MYSQL_PASSWORD=${SECRET_PASS} --name "${BUILD_ID}php" intern/php
                """
                
            }
        }
    }
}