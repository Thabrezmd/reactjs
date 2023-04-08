pipeline {
  agent any
  stages {
    stage('Checkout') {
      steps {
        checkout([$class: 'GitSCM', branches: [[name: '*/master']], userRemoteConfigs: [[url: 'https://github.com/Thabrezmd/reactjs.git']]])
      }
    }
  }
    stage('Build') {
      steps {
        sh 'npm install'
        sh 'npm run build'
      }
    }
     environment {
            CI = 'true'
        }
    // stages {
       // stage('Build') {
        //    steps {
         //       sh 'npm install'
          //  }
        //}
    //}
        stage('Test') {
                    steps {
                        sh './jenkins/scripts/test.sh'
                    }
                }
                stage('Deliver') {
                            steps {
                                sh './jenkins/scripts/deliver.sh'
                                input message: 'Finished using the web site? (Click "Proceed" to continue)'
                                sh './jenkins/scripts/kill.sh'
                            }
                        }
         stage('Stage-9 : Deployment - Deploy a Artifact devops-3.0.0-SNAPSHOT.war file to Tomcat Server') { 
            steps {
                sh 'curl -u thabrez:Tabrez@99 -T target/**.war "http://43.205.94.253:8080/manager/text/deploy?path=/reactjs&update=true"'
            }
        }                
    }
