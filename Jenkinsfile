pipeline {
  agent any
  stages {
    stage('Git checkout') {
      steps {
        git(url: 'https://github.com/suryakiran349/aks-cluster', branch: 'master')
      }
    }

    stage('terraform init') {
      steps {
        sh 'sh \'terraform init\''
      }
    }

    stage('terraform validate') {
      steps {
        sh 'sh \'terraform validate\''
      }
    }

    stage('terraform plan') {
      agent any
      steps {
        sh 'sh \'terraform plan --auto-approve\''
      }
    }

  }
}