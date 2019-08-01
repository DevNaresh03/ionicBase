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
     sh 'npm rebuild node-sass'
      sh 'ionic cordova build --release android'
   }
  }
  stage('Publish Android') {
     steps {
    echo "Publish Android API Action"
   }
  }

 

   stage('Publish iOS') {
      steps {
        
      sh 'ionic cordova ios --device --release --developmentTeam="AN2U6TVXSW" --packageType="development" --codeSignIdentity="release"'
       echo 'iOS: Starting Build'
                        // Installing Cocoa Pods, if used, may or may not be
                        // handled by Ionic. At this time I'm unsure.
                        // sh 'pod install'
                        // If using Cocoa Pods, you will need to use -workspace
                        // with .xcworkspace instead
    sh 'xcodebuild -project platforms/ios/MyApp.xcodeproj -scheme MyApp clean archive -archivePath MyApp.xcarchive'
    sh 'xcodebuild -exportArchive -archivePath MyApp.xcarchive -exportOptionsPlist exportOptions.plist -exportPath .'
    }
   }

   



 }
}
