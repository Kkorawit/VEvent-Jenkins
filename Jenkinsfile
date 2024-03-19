pipeline {
    agent any
    stages {
        stage('Update Datetime') {
            steps {
                script {
                    sh"docker exec ${ENV_DEV}-db-vevent mysql -u ${ROOT_USER} -p ${ROOT_PAS} vevent -e \"SELECT * FROM users;\""
                    
                }
            }
        }
    }
}