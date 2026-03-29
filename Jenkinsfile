pipeline {
    agent any   // runs on Jenkins master

    stages {

        stage('Deploy 2026Q1') {
            steps {
                git branch: '2026Q1', url: 'https://github.com/127rutu/docker-repos.git'
                sh '''
                    docker rm -f c1 || true
                    docker run -d --name c1 -p 80:80 \
                        -v ${WORKSPACE}:/usr/local/apache2/htdocs/ \
                        httpd:latest
                '''
            }
        }

        stage('Deploy 2026Q2') {
            steps {
                git branch: '2026Q2', url: 'https://github.com/127rutu/docker-repos.git'
                sh '''
                    docker rm -f c2 || true
                    docker run -d --name c2 -p 90:80 \
                        -v ${WORKSPACE}:/usr/local/apache2/htdocs/ \
                        httpd:latest
                '''
            }
        }

        stage('Deploy 2026Q3') {
            steps {
                git branch: '2026Q3', url: 'https://github.com/127rutu/docker-repos.git'
                sh '''
                    docker rm -f c3 || true
                    docker run -d --name c3 -p 8090:80 \
                        -v ${WORKSPACE}:/usr/local/apache2/htdocs/ \
                        httpd:latest
                '''
            }
        }

    }
}
