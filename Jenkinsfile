pipeline {
    agent any
    stages {
        stage("Build")
        {
            steps
            {
                script {
                        echo "INFO: Building Docker Image"
                        sh "docker build -t nodejs-demo:latest ."
                        echo "INFO: Docker Image built"
                }
            }
        }
        stage("Deploy")
        {
            steps
            {
                script {
                    echo "INFO: Running new Docker image"
                    sh "docker rm -f nodejs-demo || true"
                    sh "docker run --restart alwats -p 3000:3000 -d --name nodejs-demo nodejs-demo:latest"
                    echo "INFO: Deployed"
                }
            }
        }
    }
}