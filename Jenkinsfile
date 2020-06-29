pipeline {

  agent { label 'nginx' }

  stages {

    stage('Checkout Source') {
      steps {
        git url:'https://github.com/rxwminhaj/eks.git', branch:'master'
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
