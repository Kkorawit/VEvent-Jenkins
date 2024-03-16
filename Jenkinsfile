pipeline {
    agent any
    stages {
        stage("Build")
        {
            steps
            {
                script {
                        echo "INFO: Building Docker Image"
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
                    echo "INFO: Deployed"
                }
            }
        }
    }
}