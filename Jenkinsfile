pipeline {
  agent any
  stages {
    stage('Checkout') {
      steps {
        checkout([$class: 'GitSCM', branches: [[name: '*/master']], userRemoteConfigs: [[url: 'https://github.com/Thabrezmd/reactjs.git']]])
      }
    }
    stage('Build') {
      steps {
        sh 'npm install'
        sh 'npm run build'
      }
    }
   // stage('Stage-9 : Deployment - Deploy a Artifact devops-3.0.0-SNAPSHOT.war file to Tomcat Server') { 
           // steps {
           //     sh 'curl -u admin:redhat@123 -T target/**.war "http://13.232.43.217:8080/manager/text/deploy?path=/reactjs&update=true"'
         //   }
       // } 
    // stage('Deploy to Tomcat') {
    // steps {
     //   sh 'curl -u admin:redhat@123 -T <path_to_war_file> http://13.232.43.217:8080/manager/text/deploy?path=/reactjs&update=true'
   // }
// }

}
}
