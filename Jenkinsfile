pipeline {
    agent any
    stages {
        stage('Update Datetime') {
            steps {
                script {
                    def updateDate = """
                    SET SQL_SAFE_UPDATES = 0;
                    UPDATE events SET event_status = IF(NOW()<start_date and NOW()<end_date,'UP',event_status);
                    UPDATE events SET event_status = IF(NOW()>start_date and NOW()<end_date,'ON',event_status); 
                    UPDATE events SET event_status = IF(NOW()>start_date and NOW()>end_date,'CO',event_status);
                    SET SQL_SAFE_UPDATES = 1;"""
                    sh"docker exec ${ENV_DEV}-db-vevent mysql -u ${ROOT_USER} -p'${ROOT_PAS_DEV}' -e \"${updateDate}\""
                    
                }
            }
        }
    }
}