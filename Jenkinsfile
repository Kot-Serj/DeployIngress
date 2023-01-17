pipeline { 
    agent any

    environment {
        DOCKER_CREDENTIALS = credentials('docker-login')
        REPOSITORY ='https://index.docker.io'
    }

    stages {
        
        stage ('Deploy to k8s') {
            steps {
                 sh "kubectl apply -f ~/workspace/k8s/Ingress/roles.yaml"
                 sh "kubectl apply -f ~/workspace/k8s/Ingress/class.yaml"
                 sh "kubectl apply -f ~/workspace/k8s/Ingress/ingress.yaml"
            }
        }
    }
}