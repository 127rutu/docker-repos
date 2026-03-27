pipeline {
    agent none

    stages {

        // Slave 1 deployments
        stage('Deploy 2026Q1 on Slave 1') {
            agent { label 'slave-1' }
            steps {
                git branch: '2026Q1', url: 'https://github.com/127rutu/docker-repos.git'
                sh '''
                docker rm -f c1 || true
                docker run -d --name c1 -p 80:80 httpd:latest
                scp ./index.html root@172.31.44.36:/tmp/index.html
                ssh root@172.31.44.36 "docker cp /tmp/index.html c1:/usr/local/apache2/htdocs/index.html"
                '''
            }
        }

        stage('Deploy 2026Q2 on Slave 1') {
            agent { label 'slave-1' }
            steps {
                git branch: '2026Q2', url: 'https://github.com/127rutu/docker-repos.git'
                sh '''
                docker rm -f c2 || true
                docker run -d --name c2 -p 90:80 httpd:latest
                scp ./index.html root@172.31.44.36:/tmp/index.html
                ssh root@172.31.44.36 "docker cp /tmp/index.html c2:/usr/local/apache2/htdocs/index.html"
                '''
            }
        }

        stage('Deploy 2026Q3 on Slave 1') {
            agent { label 'slave-1' }
            steps {
                git branch: '2026Q3', url: 'https://github.com/127rutu/docker-repos.git'
                sh '''
                docker rm -f c3 || true
                docker run -d --name c3 -p 8090:80 httpd:latest
                scp ./index.html root@172.31.44.36:/tmp/index.html
                ssh root@172.31.44.36 "docker cp /tmp/index.html c3:/usr/local/apache2/htdocs/index.html"
                '''
            }
        }

        // Slave 2 deployments
        stage('Deploy 2026Q1 on Slave 2') {
            agent { label 'slave-2' }
            steps {
                git branch: '2026Q1', url: 'https://github.com/127rutu/docker-repos.git'
                sh '''
                docker rm -f c1 || true
                docker run -d --name c1 -p 80:80 httpd:latest
                scp ./index.html root@172.31.14.233:/tmp/index.html
                ssh root@172.31.14.233 "docker cp /tmp/index.html c1:/usr/local/apache2/htdocs/index.html"
                '''
            }
        }

        stage('Deploy 2026Q2 on Slave 2') {
            agent { label 'slave-2' }
            steps {
                git branch: '2026Q2', url: 'https://github.com/127rutu/docker-repos.git'
                sh '''
                docker rm -f c2 || true
                docker run -d --name c2 -p 90:80 httpd:latest
                scp ./index.html root@172.31.14.233:/tmp/index.html
                ssh root@172.31.14.233 "docker cp /tmp/index.html c2:/usr/local/apache2/htdocs/index.html"
                '''
            }
        }

        stage('Deploy 2026Q3 on Slave 2') {
            agent { label 'slave-2' }
            steps {
                git branch: '2026Q3', url: 'https://github.com/127rutu/docker-repos.git'
                sh '''
                docker rm -f c3 || true
                docker run -d --name c3 -p 8090:80 httpd:latest
                scp ./index.html root@172.31.14.233:/tmp/index.html
                ssh root@172.31.14.233 "docker cp /tmp/index.html c3:/usr/local/apache2/htdocs/index.html"
                '''
            }
        }

    }
}
