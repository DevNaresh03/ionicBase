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
      sh 'ionic cordova build android'
   }
  }
  stage('Publish Android') {
     steps {
    echo "Publish Android API Action"
   }
  }

  stage('IOS Build') {
   steps {
      sh 'ionic cordova build ios'
     } 
  }

   stage('Publish iOS') {
      steps {
       echo "Publish iOS Action"
    }
   }

   



 }
}
