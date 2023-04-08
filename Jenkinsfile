pipeline {
  agent any
  
  stages {
    stage('Build') {
      steps {
        sh 'npm install'
        sh 'npm run build'
      }
    }
    
    stage('Deploy') {
      steps {
        sh '''
          curl -u admin:redhat@123 "http://13.232.43.217:8080/manager/text/undeploy?path=/reactjs"
          curl -u admin:redhat@123 -T build/*.war "http://13.232.43.217:8080/manager/text/deploy?path=/reactjs&update=true"
        '''
      }
    }
  }
}
