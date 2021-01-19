pipeline {
    agent any
    
    tools
    {
       maven "mvn"
    }
     
    stages {
      stage('checkout') {
           steps {
             
                git 'https://github.com/urc1712/cicddemo.git'
             
          }
      }
     
        
         stage('Execute Maven') {
           steps {
             
                sh 'mvn package'             
          }
        }
        
        stage('deploy') {
            steps {
                ansiblePlaybook disableHostKeyChecking: true, installation: 'ansible', inventory: '/home/urc/cicddemo/inventories/prod', playbook: '/home/urc/cicddemo/main.yml'
            }
            
        }
         
        
        
        
    }
}
