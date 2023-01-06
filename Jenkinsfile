pipeline {
    agent {
        label 'snowflake2'
    } 
      
       
    stages {
        stage('Run schemachange') {
            steps {
                sh "sudo pip install schemachange --upgrade"
                sh "sudo schemachange -f migrations -a ${SF_ACCOUNT} -u ${SF_USERNAME} -r ${SF_ROLE} -w ${SF_WAREHOUSE} -d ${SF_DATABASE} -c ${SF_DATABASE}.SCHEMACHANGE.CHANGE_HISTORY --create-change-history-table"
            }
        }
    }
}
