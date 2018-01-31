node {
    stage('Clone Repository') {
        checkout scm
    }

    stage('Deploy kube-lego') {
        sh "gcloud container clusters get-credentials ${env.CLUSTER_NAME} --project=${env.PROJECT_ID} --zone=australia-southeast1-a"
        sh "kubectl apply -f gce/lego/00-namespace.yaml"
        sh "kubectl apply -f gce/lego/configmap.yaml"
        sh "kubectl apply -f gce/lego/deployment.yaml"
    }
}