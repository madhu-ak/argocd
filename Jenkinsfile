pipeline {
  agent any
  
  stages {
    stage('Checkout') {
      steps {
        sh 'echo passed'
        //git branch: 'main', url: 'https://github.com/madhu-ak/argocd.git'
      }
    }
    stage('Build and Test') {
      steps {
        sh 'ls -ltr'
        // build the project and create a JAR file
        sh 'go-app'
      }
    }

    stage('Build docker'){
        steps{
            echo 'Building Docker image'
            sh 'docker build -t goapp'
        }
    }
    
  }
}
