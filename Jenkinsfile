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
      sh 'ionic cordova platform rm android'
      sh 'ionic cordova platform add android'
      sh 'ionic cordova build android --release'
   }
  }
  stage('Publish Android') {
     steps {
    echo "Publish Android API Action"
   }
  }

  stage('IOS Build') {
   steps {
      sh 'ionic cordova build ios --release'
     } 
  }

   stage('Publish iOS') {
      steps {
       echo "Publish iOS Action"
    }
   }

   



 }
}
