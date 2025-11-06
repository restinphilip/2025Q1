pipeline {
    agent any

    stages {
        stage('start_docker') {
            steps {
                sh '''
                    yum install docker -y
                    systemctl restart docker
                '''
            }
        }

        stage('httpd-container') {
            steps {
                sh '''
                    docker run docker run -dp 80:80 --name test httpd
                    cp index.html test:/usr/local/apache2/htdocs
                '''
            }
        }
    }
}
