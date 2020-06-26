pipeline {
    agent any 
    stages {
        stage('clone repo and Apply Kubernetes files') { 
            withKubeConfig([credentialsId: 'rxwminhaj',
                    serverUrl: 'https://api.github.com',
                    clusterName: 'nginxcluster',
                    namespace: 'default'
                    ]) {              
                sh "git clone https://github.com/rxwminhaj/eks.git"
                sh "kubectl install"
                sh "kubectl create -f nginx.yaml"
                sh "kubectl create -f nginx-svc.yaml"
                sh "kubectl get service -o wide"
                sh "kubectl get pods"
                
            }
        }
      
    }
}
