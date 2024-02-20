pipeline{
    agent any
        stages{
            stage("k8s"){
                steps{
                    withKubeCredentials(kubectlCredentials: [[caCertificate: '', clusterName: 'cluster', contextName: '', credentialsId: 'k8s', namespace: 'default', serverUrl: 'https://D4568959FAF7F4525DC2C46AE757C5DD.gr7.eu-west-2.eks.amazonaws.com']]) 
                    {
                    sh 'curl -LO "https://storage.googleapis.com/kubernetes-release/release/v1.20.5/bin/linux/amd64/kubectl"'
                    sh 'chmod u+x ./kubectl'
                    sh './kubectl apply -f deployment.yaml'
                    }
                }    
        }
    }
}
