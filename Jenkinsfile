pipeline {
    agent any

    stages {

        stage('Deploy 2026Q1') {
            steps {
                git branch: '2026Q1', url: 'https://github.com/127rutu/docker-repos.git'
                script {
                    sh '''
                    docker rm -f c1 || true
                    docker run -d --name c1 -p 8081:80 httpd:latest
                    docker exec c1 rm -rf /usr/local/apache2/htdocs/*
                    docker cp . c1:/usr/local/apache2/htdocs/
                    '''
                }
            }
        }

        stage('Deploy 2026Q2') {
            steps {
                git branch: '2026Q2', url: 'https://github.com/127rutu/docker-repos.git'
                script {
                    sh '''
                    docker rm -f c2 || true
                    docker run -d --name c2 -p 8082:80 httpd:latest
                    docker exec c2 rm -rf /usr/local/apache2/htdocs/*
                    docker cp . c2:/usr/local/apache2/htdocs/
                    '''
                }
            }
        }

        stage('Deploy 2026Q3') {
            steps {
                git branch: '2026Q3', url: 'https://github.com/127rutu/docker-repos.git'
                script {
                    sh '''
                    docker rm -f c3 || true
                    docker run -d --name c3 -p 8090:80 httpd:latest
                    docker exec c3 rm -rf /usr/local/apache2/htdocs/*
                    docker cp . c3:/usr/local/apache2/htdocs/
                    '''
                }
            }
        }
    }
}
