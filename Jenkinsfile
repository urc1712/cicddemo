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
                ansiblePlaybook disableHostKeyChecking: true, installation: 'ansible', inventory: '/var/lib/jenkins/workspace/ci-cd/inventories/prod/hosts', playbook: '/var/lib/jenkins/workspace/ci-cd/main.yml'
            }
            
        }
         
        
        
        
    }
}
