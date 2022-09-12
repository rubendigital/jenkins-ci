pipeline {
    agent any 
    parameters {
        choice(name: "SERVER", choices: ["ALL", "SERVER 1", "SERVER 2", "SERVER 3"])
    }
    stages {
        stage('Parallel Execution') {
                parallel {
                    stage('Restore IN SERVER 1') {
                        when {
                            expression { params.SERVER == 'SERVER 1' }
                        }
                        steps {
                            sh('echo Restore IN SERVER 1')
                        }
                    }
                    stage('Restore IN SERVER 2') {
                         when {
                            expression { params.SERVER == 'SERVER 2' }
                        }
                        steps {
                            sh('echo 2')
                        }
                    }
                    stage('Restore IN SERVER 2') {
                         when {
                            expression { params.SERVER == 'SERVER 3' }
                        }
                        steps {
                            sh('echo Restore IN SERVER 3')
                        }
                    }
            }
        }
    }
}
