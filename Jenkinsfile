pipeline {
    agent {
        label 'snowflake2'
    } 
      
       
    stages {
        stage('Run schemachange') {
            steps {
                sh "pip install schemachange --upgrade"
                sh "python3 --version"
                sh "pip show schemachange"
                sh "schemachange -f migrations -a ${SF_ACCOUNT} -u ${SF_USERNAME}"
                
           //     sh "schemachange -f migrations -a ${SF_ACCOUNT} -u ${SF_USERNAME} -r ${SF_ROLE} -w ${SF_WAREHOUSE} -d ${SF_DATABASE} -c ${SF_DATABASE}.SCHEMACHANGE.CHANGE_HISTORY --create-change-history-table"
            }
        }
    }
}
