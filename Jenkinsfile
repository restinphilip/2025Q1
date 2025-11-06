pipeline {
    agent any

    stages {
        stage('start_docker') {
            steps {
                sh '''
                    sudo yum install docker -y
                    sudo service docker start
                '''
            }
        }

        stage('port-binding') {
            steps {
                sh '''
                    sudo docker run -dp 80:80 --name test httpd
                    
                '''
            }
        }
        
        stage('httpd-container') {
            steps {
                sh '''
                    sudo docker cp index.html test:/usr/local/apache2/htdocs/
                '''
            }
        }
    }
}
