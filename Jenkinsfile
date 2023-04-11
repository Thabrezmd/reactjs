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
          curl --manual -u thabrez:Tabrez@99 "http://3.110.87.198:8080/manager/text/undeploy?path=/reactjs"
          curl --manual -u thabrez:Tabrez@99 -T build/*.war "http://3.110.87.198:8080/manager/text/deploy?path=/reactjs&update=true"
        '''
      }
    }
  }
}
