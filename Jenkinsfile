pipeline {
    agent any 
    stage('Clone and List pods') { 
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
