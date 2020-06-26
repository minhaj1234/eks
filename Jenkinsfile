pipeline {
    agent any 
    stages {
        stage('clone repo and create nginx service') { 
            steps {
                sh "git clone https://github.com/rxwminhaj/eks.git"
                sh "kubectl create -f nginx.yaml"
                sh "kubectl create -f nginx-svc.yaml"
                sh "kubectl get service -o wide"
                
            }
        }
      
    }
}
