pipeline {

  agent { label 'kubepods' }

  stages {

    stage('Checkout Source') {
      steps {
        git url:'https://github.com/rxwminhaj/eks.git'
      }
    }

    stage('Deploy App') {
      steps {
        script {
          kubernetesDeploy(configs: "nginx.yaml", kubeconfigId: "mykubeconfig")
        }
      }
    }

  }

}
