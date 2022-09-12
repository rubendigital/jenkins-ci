pipeline {
    agent any 
    parameters {
        choice(name: "SERVER", choices: ["1", "2", "3"])
    }
    stages {
        stage('Parallel Execution') {
                parallel {
                    stage('Restore IN SERVER 1') {
                        when {
                            expression { params.SERVER == '1' }
                        }
                        steps {
                            sh('echo 1')
                        }
                    }
                    stage('Restore IN SERVER 2') {
                         when {
                            expression { params.SERVER == '2' }
                        }
                        steps {
                            sh('echo 2')
                        }
                    }
                    stage('Restore IN SERVER 3') {
                         when {
                            expression { params.SERVER == '3' }
                        }
                        steps {
                            sh('echo ${SERVER}')
                        }
                    }
            }
        }
    }
}
