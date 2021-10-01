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
        withCredentials([usernamePassword(credentialsId: 'dockerhub', usernameVariable: 'USERNAME', passwordVariable: 'PASSWORD')]) {
        sh """
          docker build . -f dockerfile -t ziadamr14/sprints_jenkins_course:latest
          docker login -u ${USERNAME} -p ${PASSWORD}
          docker push ziadamr14/sprints_jenkins_course:latest
          
        
        """
        
        }
      }
      
    }
    
    stage('deployment') {
      steps {
        sh """
          docker run -d -p 3000:3000 ziadamr14/sprints_jenkins_course:latest
          
        
        """
        
      }
      
    }
    
  }
  
}

        
        
    
