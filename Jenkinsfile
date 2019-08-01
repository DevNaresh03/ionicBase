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

   stage('iOS Build') {
      sh 'ionic cordova build ios --prod --release -- --developmentTeam="AN2U6TVXSW" --codeSignIdentity="iPhone Developer" --packageType="app-store"' 
   }

//    stage('Android Build') {
//    steps {
//      sh 'npm rebuild node-sass'
//       sh 'ionic cordova build --release android'
//    }
//   }
//   stage('Publish Android') {
//      steps {
//     echo "Publish Android API Action"
//    }
//   }


//    stage('Publish iOS') {
//       steps {
//       sh 'ionic cordova build ios --developmentTeam="AN2U6TVXSW" --packageType="development" --codeSignIdentity="release"'
               
//     sh 'xcodebuild -project platforms/ios/MyApp.xcodeproj -scheme MyApp clean archive -archivePath MyApp.xcarchive'
//     sh 'xcodebuild -exportArchive -archivePath MyApp.xcarchive -exportOptionsPlist exportOptions.plist -exportPath .'
//     }
//    }

   



 }
}
