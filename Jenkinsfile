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
                            def remote = [:]
                            remote.name = 'test'
                            remote.host = 'test.domain.com'
                            remote.user = 'root'
                            remote.password = 'password'
                            remote.allowAnyHosts = true
                            echo 'Restore IN SERVER 1'
                        }
                    }
                    stage('Restore IN SERVER 2') {
                         when {
                            expression { params.SERVER == 'SERVER 2' }
                        }
                        steps {
                            def remote = [:]
                            remote.name = 'test'
                            remote.host = 'test.domain.com'
                            remote.user = 'root'
                            remote.password = 'password'
                            remote.allowAnyHosts = true
                            echo 'Restore IN SERVER 1'
                            
                            echo 'Restore IN SERVER 2'
                        }
                    }
                    stage('Restore IN SERVER 3') {
                         when {
                            def remote = [:]
                            remote.name = 'test'
                            remote.host = 'test.domain.com'
                            remote.user = 'root'
                            remote.password = 'password'
                            remote.allowAnyHosts = true
                            echo 'Restore IN SERVER 1'                             
                            expression { params.SERVER == 'SERVER 3' }
                        }
                        steps {
                            echo 'Restore IN SERVER 3'
                        }
                    }
            }
        }
    }
}
