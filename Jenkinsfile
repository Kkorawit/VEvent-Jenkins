pipeline {
    agent any
    stages {
        stage('Update Datetime') {
            steps {
                script {
                    def mysqlCommand = "mysql -h capstone23.sit.kmutt.ac.th/kw1 -P 3306 -u root -p 'cp23-db-Vevent' vevent -e \"SELECT title From events;\""
                    
                    def process = mysqlCommand.execute()
                    process.waitFor()
                    
                    if (process.exitValue() == 0) {
                        println "Datetime field updated successfully"
                    } else {
                        error "Failed to update datetime field"
                    }
                }
            }
        }
    }
}