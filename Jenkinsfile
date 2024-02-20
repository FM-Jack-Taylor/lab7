pipeline{
    agent any
        stages{
            stage("k8s"){
                steps{
                    withKubeCredentials(kubectlCredentials: [[caCertificate: '', clusterName: 'cluster', contextName: '', credentialsId: 'k8s', namespace: 'default', serverUrl: 'https://ec2-13-40-199-250.eu-west-2.compute.amazonaws.com']]) 
                    {
                    sh 'curl -LO "https://storage.googleapis.com/kubernetes-release/release/v1.20.5/bin/linux/amd64/kubectl"'
                    sh 'chmod u+x ./kubectl'
                    sh './kubectl task2-t1-deployment.yaml'
                    sh './kubectl get pods'
                    }
                }    
        }
    }
}
