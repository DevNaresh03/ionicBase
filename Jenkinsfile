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
      steps {
      sh 'ionic cordova build ios --prod --release --developmentTeam="AN2U6TVXSW" --provisioningProfile="4134a6f1-c23d-4afd-aa7f-cbff6c690099" --codeSignIdentity="iPhone Developer" --packageType="development"' 

      //sh 'ionic cordova build ios --prod --release --developmentTeam="AN2U6TVXSW" --provisioningProfile="1a313fff-609a-4686-a731-9524f0a40504" --codeSignIdentity="iPhone Developer" --packageType="app-store"' 
      sh 'xcodebuild -project platforms/ios/MyApp.xcodeproj -scheme MyApp clean archive -archivePath MyApp.xcarchive'
      sh 'xcodebuild -exportArchive -archivePath MyApp.xcarchive -exportOptionsPlist exportOptions.plist -exportPath .'
   }
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
