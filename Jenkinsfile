pipeline {
  agent any
  
  tools {
    maven 'Maven'
  }
  
  stages {
    stage('Initialize'){
      steps {
        sh '''
          echo "PATH = $(PATH)"
          echo "M2_HOME = $(M2_HOME)"
        '''
      }
    }
    stage('Build') {
      steps {
        sh 'mvn clean package'
      }
    }
    
    stage ('Deploy-to-Tomcat'){
      steps {
        sh 'cp target/*.war /home/raju/Downloads/apache-tomcat-8.5.84/webapps/WebApp1.war'
      }
    }
  }
}
