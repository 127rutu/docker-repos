pipeline {
    agent any

    stages {
        stage('Checkout 2026Q1') {
            steps {
                git branch: '2026Q1', url: 'https://github.com/127rutu/docker-repos.git'
            }
        }

        stage('Deploy to c1') {
            steps {
                script {
                    docker.image('httpd').run("--name c1 -dp 80:80")
                    docker.image('httpd').inside("--name c1") {
                        sh 'cp /workspace/index.html /usr/local/apache2/htdocs/'
                    }
                }
            }
        }

        stage('Checkout 2026Q2') {
            steps {
                git branch: '2026Q2', url: 'https://github.com/127rutu/docker-repos.git'
            }
        }

        stage('Deploy to c2') {
            steps {
                script {
                    docker.image('httpd').run("--name c2 -dp 90:80")
                    docker.image('httpd').inside("--name c2") {
                        sh 'cp /workspace/index.html /usr/local/apache2/htdocs/'
                    }
                }
            }
        }

        stage('Checkout 2026Q3') {
            steps {
                git branch: '2026Q3', url: 'https://github.com/127rutu/docker-repos.git'
            }
        }

        stage('Deploy to c3') {
            steps {
                script {
                    docker.image('httpd').run("--name c3 -dp 8080:80")
                    docker.image('httpd').inside("--name c3") {
                        sh 'cp /workspace/index.html /usr/local/apache2/htdocs/'
                    }
                }
            }
        }
    }
}
