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
  stage('IOS Build') {
   steps {
     sh 'env'
    // credentialsId and url must also be set
    echo 'iOS: Setup iOS Env. variables'
    sh '/usr/bin/security list-keychains -s /Users/NareshBojja⁩/Library/Keychains/login.keychain'
    sh '/usr/bin/security default-keychain -d user -s /Users/NareshBojja⁩/Library/Keychains/login.keychain'
    sh '/usr/bin/security unlock-keychain -p $KEYCHAIN_PASSWORD /Users/NareshBojja⁩/Library/Keychains/login.keychain'

    echo 'iOS: Starting Install'
    sh 'npm install'
    sh 'ionic cordova platform add ios --nosave'

    // May need to update --prod / --release for debugging
    // purposes for some environments
    sh 'ionic cordova build ios -- --developmentTeam="$TEAM_ID" --provisioningProfile="$PROVISIONING_PROFILE" --codeSignIdentity="$CODE_SIGN_IDENTITY"'

    echo 'iOS: Starting Build'
    // Installing Cocoa Pods, if used, may or may not be
    // handled by Ionic. At this time I'm unsure.
    // sh 'pod install'
    // If using Cocoa Pods, you will need to use -workspace
    // with .xcworkspace instead

    sh 'xcodebuild -project platforms/ios/$APP_NAME.xcodeproj -scheme $APP_NAME clean archive -archivePath $APP_NAME.xcarchive'
    sh 'xcodebuild -exportArchive -archivePath $APP_NAME.xcarchive -exportOptionsPlist exportOptions.plist -exportPath .'
}
  }

 stage('Android Build') {
   steps {
      sh 'ionic cordova platform add android'
      sh 'ionic cordova build android'
   }
  }

 
  



 }
}
