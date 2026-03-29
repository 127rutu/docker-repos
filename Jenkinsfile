pipeline {
    agent none

    stages {

        // -------------------- Slave 1 --------------------
        stage('Deploy 2026Q1 on Slave 1') {
            agent { label 'slave-1' }
            steps {
                git branch: '2026Q1', url: 'https://github.com/127rutu/docker-repos.git'
                sh '''
                    docker rm -f c1 || true
                    docker volume rm v1 || true
                    docker volume create v1
                    docker run -d --name c1 -p 80:80 -v v1:/usr/local/apache2/htdocs/ httpd:latest
                    docker cp . c1:/usr/local/apache2/htdocs/
                '''
            }
        }

        stage('Deploy 2026Q2 on Slave 1') {
            agent { label 'slave-1' }
            steps {
                git branch: '2026Q2', url: 'https://github.com/127rutu/docker-repos.git'
                sh '''
                    docker rm -f c2 || true
                    docker volume rm v2 || true
                    docker volume create v2
                    docker run -d --name c2 -p 90:80 -v v2:/usr/local/apache2/htdocs/ httpd:latest
                    docker cp . c2:/usr/local/apache2/htdocs/
                '''
            }
        }

        stage('Deploy 2026Q3 on Slave 1') {
            agent { label 'slave-1' }
            steps {
                git branch: '2026Q3', url: 'https://github.com/127rutu/docker-repos.git'
                sh '''
                    docker rm -f c3 || true
                    docker volume rm v3 || true
                    docker volume create v3
                    docker run -d --name c3 -p 8090:80 -v v3:/usr/local/apache2/htdocs/ httpd:latest
                    docker cp . c3:/usr/local/apache2/htdocs/
                '''
            }
        }

        // -------------------- Slave 2 --------------------
        stage('Deploy 2026Q1 on Slave 2') {
            agent { label 'slave-2' }
            steps {
                git branch: '2026Q1', url: 'https://github.com/127rutu/docker-repos.git'
                sh '''
                    docker rm -f c1 || true
                    docker volume rm v1 || true
                    docker volume create v1
                    docker run -d --name c1 -p 80:80 -v v1:/usr/local/apache2/htdocs/ httpd:latest
                    docker cp . c1:/usr/local/apache2/htdocs/
                '''
            }
        }

        stage('Deploy 2026Q2 on Slave 2') {
            agent { label 'slave-2' }
            steps {
                git branch: '2026Q2', url: 'https://github.com/127rutu/docker-repos.git'
                sh '''
                    docker rm -f c2 || true
                    docker volume rm v2 || true
                    docker volume create v2
                    docker run -d --name c2 -p 90:80 -v v2:/usr/local/apache2/htdocs/ httpd:latest
                    docker cp . c2:/usr/local/apache2/htdocs/
                '''
            }
        }

        stage('Deploy 2026Q3 on Slave 2') {
            agent { label 'slave-2' }
            steps {
                git branch: '2026Q3', url: 'https://github.com/127rutu/docker-repos.git'
                sh '''
                    docker rm -f c3 || true
                    docker volume rm v3 || true
                    docker volume create v3
                    docker run -d --name c3 -p 8090:80 -v v3:/usr/local/apache2/htdocs/ httpd:latest
                    docker cp . c3:/usr/local/apache2/htdocs/
                '''
            }
        }

    }
}
