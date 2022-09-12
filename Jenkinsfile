pipeline {
    agent any 
    enviroment {
        config = readJSON file: 'servers.json'
    }
    parameters {
        choice(name: "SERVER", choices: ["ALL", "SERVER 1", "SERVER 2", "SERVER 3"])
    }
    stages {
         stage('Parallel Execution') {
             when { expression { params.SERVER == 'ALL' }}
             parallel {
                 config['SERVERS'].each { item -> 
                     stage('Restore IN SERVER ${item}') {                        
                        steps {
                            echo 'Restore IN SERVER ${item}';
                        }
                 }
              }
            }
         }
        
    }
}
