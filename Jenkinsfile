pipeline {
    agent {
        agent any
    }
    stages {
        stage('Build Maven') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/madhu-ak/argocd.git']]])
                dir('/go-app/Jenkinsfile')

            }
        }
        stage('Build docker image') {
            steps {
                script {
                    sh 'docker build -t madhsunv/goapp .'
                }
            }
        }
        stage('Push image to hub') {
            steps {
                script {
                    sh 'docker login -u dock_user -p dock_password'
                    sh 'docker push madhsunv/goapp' // Corrected line
                }
            }
        }


        }
    }
