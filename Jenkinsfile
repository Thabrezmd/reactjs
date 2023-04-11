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
          curl --manual -u admin:redhat@123 "http://15.206.122.81:8080/manager/text/undeploy?path=/reactjs"
          curl --manual -u admin:redhat@123 -T build/*.war "http://15.206.122.81:8080/manager/text/deploy?path=/reactjs&update=true"
        '''
      }
    }
  }
}
