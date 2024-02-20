pipeline{
    agent any
        stages{
            stage("k8s"){
                steps{
                    withKubeCredentials(kubectlCredentials: [[caCertificate: '', clusterName: 'cluster', contextName: '', credentialsId: 'k8s', namespace: 'default', serverUrl: 'https://ec2-13-40-199-250.eu-west-2.compute.amazonaws.com']]) 
                    {
                    sh './kubectl deployment.yaml'
                    }
                }    
        }
    }
}
