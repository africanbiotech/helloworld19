pipeline {
 agent any
 tools {
  maven 'M2_HOME'
 }
  stages {
    stage ('Build') {
      steps {
       sh 'mvn clean'
       sh 'mvn install'
       sh 'mvn package'
        echo "build Step"
        sleep 9
      
      }
    
    }
  
    stage ('success') {
      steps { 
        echo "success Step"
        sh 'mvn test'
        sleep 10
      
      }
    
    }
   stage ('Deploy') {
      steps { 
        echo "deploy Step"
        sh 'mvn test'
        sleep 10
      
      }
    
    }
   
  }
  
  
}
