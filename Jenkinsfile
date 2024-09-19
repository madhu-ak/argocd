pipeline {
    agent any
        
    stages {
        stage('Build Maven') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/madhu-ak/argocd.git']]])
                sh 'cd /go-app/'
            }
        }
        stage('Build docker image') {
            steps {
                script {
                    sh 'docker build -t docker-host:5000/playground-image:public .'
                }
            }
        }
      
         
    }
}
