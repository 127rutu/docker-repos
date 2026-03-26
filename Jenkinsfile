pipeline {
    agent any

    stages {
        stage('Deploy 2026q1') {
            steps {
                git branch: '2026q1', url: 'https://github.com/127rutu/docker-repos.git'
                script {
                    sh 'docker rm -f c1 || true'
                    docker.image('httpd:latest').run('--name c1 -dp 80:80')
                    sh 'docker exec c1 mkdir -p /usr/local/apache2/htdocs/2026q1'
                    sh 'docker cp . c1:/usr/local/apache2/htdocs/2026q1/'
                }
            }
        }

        stage('Deploy 2026q2') {
            steps {
                git branch: '2026q2', url: 'https://github.com/127rutu/docker-repos.git'
                script {
                    sh 'docker rm -f c2 || true'
                    docker.image('httpd:latest').run('--name c2 -dp 90:80')
                    sh 'docker exec c2 mkdir -p /usr/local/apache2/htdocs/2026q2'
                    sh 'docker cp . c2:/usr/local/apache2/htdocs/2026q2/'
                }
            }
        }

        stage('Deploy 2026q3') {
            steps {
                git branch: '2026q3', url: 'https://github.com/127rutu/docker-repos.git'
                script {
                    sh 'docker rm -f c3 || true'
                    docker.image('httpd:latest').run('--name c3 -dp 8080:80')
                    sh 'docker exec c3 mkdir -p /usr/local/apache2/htdocs/2026q3'
                    sh 'docker cp . c3:/usr/local/apache2/htdocs/2026q3/'
                }
            }
        }
    }
}
