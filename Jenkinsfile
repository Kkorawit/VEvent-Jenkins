pipeline {
    agent any
    stages {
        stage('Update Datetime') {
            steps {
                script {
                    sh"docker exec -it ${ENV_DEV}-db-vevent mysql -u ${ROOT_USER} -p'${ROOT_PAS}' -e \"SELECT * FROM vevent.users;\""
                    
                }
            }
        }
    }
}