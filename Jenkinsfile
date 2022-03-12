pipeline {
 agent any
 triggers {
   pollSCM '* * * * *'
 }
 tools {
  maven 'M2_HOME'
 }
 environment {
    registry = "africanbiotech/jenkins_pipeline"
    registryCredential = 'deploy'
}

  stages {
    stage ('Build') {
      steps {
       sh 'mvn clean'
       sh 'mvn install'
       sh 'mvn package'
       sh 'mvn test'
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
   
    stage ('Building image') {
      steps{
        script {
        docker.build registry + ":$BUILD_NUMBER"
      }
    }
  }
   
  }
  
  
}
