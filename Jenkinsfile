pipeline {
    agent any

    stages {

        stage('Deploy 2026Q1') {
            steps {
                git branch: '2026Q1', url: 'https://github.com/127rutu/docker-repos.git'
                script {
                    sh '''
                    # Remove old container & volume
                    docker rm -f c1 || true
                    docker volume rm v1 || true

                    # Create new volume
                    docker volume create v1

                    # Run container with volume
                    docker run -d --name c1 -p 80:80 \
                      -v v1:/usr/local/apache2/htdocs/ \
                      httpd:latest

                    # Copy code into container (goes into volume)
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
                    docker volume rm v2 || true

                    docker volume create v2

                    docker run -d --name c2 -p 90:80 \
                      -v v2:/usr/local/apache2/htdocs/ \
                      httpd:latest

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
                    docker volume rm v3 || true

                    docker volume create v3

                    docker run -d --name c3 -p 8090:80 \
                      -v v3:/usr/local/apache2/htdocs/ \
                      httpd:latest

                    docker cp . c3:/usr/local/apache2/htdocs/
                    '''
                }
            }
        }
    }
}
