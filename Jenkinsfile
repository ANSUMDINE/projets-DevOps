pipeline {

    agent any

    stages {

        stage('Checkout SCM') {

            steps {

                cleanWs()

                git branch: 'main', url: 'https://github.com/ANSUMDINE/projets-DevOps.git'

            }

        }

        stage('Build image Docker') {

            steps {

                sh 'docker build -t myapp .'

            }

        }

        stage('Deploy application') {

            steps {

                sh 'docker rm -f myapp || true'

                sh 'docker run -d --name myapp -p 8088:80 myapp'

            }
