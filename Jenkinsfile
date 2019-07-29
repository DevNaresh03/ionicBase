pipeline {
   agent any
      environment {
         PATH='/usr/local/bin:/usr/bin:/bin'
      }
   stages {
      stage('NPM Setup') {
      steps {
         sh 'npm install'
      }
   }
 

 stage('Android Build') {
   steps {
      sh 'ionic cordova platform add android'
      sh 'ionic cordova build android'
   }
  }

  stage('ios Build') {
   steps {
      sh 'ionic cordova platform rm ios'
      sh 'ionic cordova platform add ios'
      sh 'ionic cordova build ios'
   }
  }

  



 }
}
