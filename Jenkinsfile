pipeline {
    agent {
        label 'slave2'
            }

    stages {
        stage('port-binding') {
            steps {
                sh '''
                    sudo docker rm -f test || true
                    sudo docker run -dp 80:80 --name test httpd
                    
                '''
            }
        }
        
        stage('httpd-container') {
            steps {
                sh '''
                    sudo docker cp index.html test:/usr/local/apache2/htdocs/
                    sudo docker exec test chmod 644 /usr/local/apache2/htdocs/index.html
                '''
            }
        }
    }
}
