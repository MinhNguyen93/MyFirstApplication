node {
    checkout scm
    stage('Compile') {
        // Compile the app and its dependencies
        sh './gradlew assembleDebug'
      
    }
    stage('Unit test') {
        // Compile and run the unit tests for the app and its dependencies
        sh './gradlew testDebugUnitTest testDebugUnitTest'

        // Analyse the test results and update the build result as appropriate
        junit '**/TEST-*.xml'
    }
    stage('Build APK') {
        // Finish building and packaging the APK
        sh './gradlew assembleDebug'

        // Archive the APKs so that they can be downloaded from Jenkins
        archiveArtifacts '**/*.apk'
        }
}

