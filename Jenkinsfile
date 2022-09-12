pipeline {
    agent any 
    parameters {
        string(name: 'SERVER', defaultValue: 'all', description: 'Server to execute Restore: ')
    }
    stages {
        stage('Restore') {
            steps {
                 sh('echo ${SERVER}')
            }
        }
    }
}
