pipeline {

  agent { label 'testpod' }

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
