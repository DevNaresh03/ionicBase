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
      sh 'ionic cordova build android --release'
   }
  }

   stage('Publish Android') {
     steps {
    echo "Publish Android API Action"
   }
  }

 }
}
