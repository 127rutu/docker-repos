pipeline {
    agent none

    stages {

        // -------------------- Slave 1 --------------------
        stage('Deploy all branches on Slave 1') {
            agent { label 'slave-1' }
            steps {
                // 2026Q1
                git branch: '2026Q1', url: 'https://github.com/127rutu/docker-repos.git'
                sh '''
                    docker volume rm v1 || true
                    docker volume create v1
                    docker run --rm -v v1:/data -v $WORKSPACE:/src busybox cp /src/index.html /data/index.html
                    docker rm -f c1 || true
                    docker run -d --name c1 -p 80:80 -v v1:/usr/local/apache2/htdocs httpd:latest
                '''

                // 2026Q2
                git branch: '2026Q2', url: 'https://github.com/127rutu/docker-repos.git'
                sh '''
                    docker volume rm v2 || true
                    docker volume create v2
                    docker run --rm -v v2:/data -v $WORKSPACE:/src busybox cp /src/index.html /data/index.html
                    docker rm -f c2 || true
                    docker run -d --name c2 -p 90:80 -v v2:/usr/local/apache2/htdocs httpd:latest
                '''

                // 2026Q3
                git branch: '2026Q3', url: 'https://github.com/127rutu/docker-repos.git'
                sh '''
                    docker volume rm v3 || true
                    docker volume create v3
                    docker run --rm -v v3:/data -v $WORKSPACE:/src busybox cp /src/index.html /data/index.html
                    docker rm -f c3 || true
                    docker run -d --name c3 -p 8090:80 -v v3:/usr/local/apache2/htdocs httpd:latest
                '''
            }
        }

        // -------------------- Slave 2 --------------------
        stage('Deploy all branches on Slave 2') {
            agent { label 'slave-2' }
            steps {
                // 2026Q1
                git branch: '2026Q1', url: 'https://github.com/127rutu/docker-repos.git'
                sh '''
                    docker volume rm v1 || true
                    docker volume create v1
                    docker run --rm -v v1:/data -v $WORKSPACE:/src busybox cp /src/index.html /data/index.html
                    docker rm -f c1 || true
                    docker run -d --name c1 -p 80:80 -v v1:/usr/local/apache2/htdocs httpd:latest
                '''

                // 2026Q2
                git branch: '2026Q2', url: 'https://github.com/127rutu/docker-repos.git'
                sh '''
                    docker volume rm v2 || true
                    docker volume create v2
                    docker run --rm -v v2:/data -v $WORKSPACE:/src busybox cp /src/index.html /data/index.html
                    docker rm -f c2 || true
                    docker run -d --name c2 -p 90:80 -v v2:/usr/local/apache2/htdocs httpd:latest
                '''

                // 2026Q3
                git branch: '2026Q3', url: 'https://github.com/127rutu/docker-repos.git'
                sh '''
                    docker volume rm v3 || true
                    docker volume create v3
                    docker run --rm -v v3:/data -v $WORKSPACE:/src busybox cp /src/index.html /data/index.html
                    docker rm -f c3 || true
                    docker run -d --name c3 -p 8090:80 -v v3:/usr/local/apache2/htdocs httpd:latest
                '''
            }
        }

    }
}
