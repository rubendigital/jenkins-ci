pipeline {
    agent any 
    parameters {
        choice(name: "SERVER", choices: ["ALL", "SERVER 1", "SERVER 2", "SERVER 3"])
    }
    stages {
         stage('Parallel Execution') {
             stage('Restore IN SERVER 1') {
                 when { expression { params.SERVER == 'SERVER 1' }}
                 steps {
                     node {
                         def remote = [:]
                         remote.name = 'test'
                         remote.host = 'test.domain.com'
                         remote.user = 'root'
                         remote.password = 'password'
                         remote.allowAnyHosts = true
                         stage('Remote SSH') {
                              sshRemove remote: remote, path: "restore_db.sh"
                           }
                      }
                 }
             }
         }
        
    }
}
