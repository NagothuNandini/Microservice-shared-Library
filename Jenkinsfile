pipeline {
    agent any

    stages {
        stage('Deploy To Kubernetes') {
            steps {
                withKubeCredentials(kubectlCredentials: [[caCertificate: '', clusterName: 'kubernetes', contextName: '', credentialsId: 'k8s-cred-test', namespace: 'webapps', serverUrl: 'https://10.0.1.62:6443']]) {
                    sh 'kubectl apply -f deployment-service.yaml -n webapps'
                }
            }
        }
        
        stage('verify Deployment') {
            steps {
                withKubeCredentials(kubectlCredentials: [[caCertificate: '', clusterName: 'kubernetes', contextName: '', credentialsId: 'k8s-cred-test', namespace: 'webapps', serverUrl: 'https://10.0.1.62:6443']]) {
                    sh 'kubectl get pods -n webapps'
                }
            }
        }
    }
}
