pipeline {
  agent any
   
  
  stages {
    
    
    stage('Preparation') {
      steps {
        
        git 'https://github.com/ZiadAmr14/jenkins_nodejs_example.git'
        
      }
      
    }
    
    
    stage('Docker Build') {
      steps {
        
        sh """
          docker build . -f dockerfile -t ziadamr14/sprintsJenkinsCourse:latest
          
        
        """
        
      }
      
    }
    
  }
  
}

        
        
    
