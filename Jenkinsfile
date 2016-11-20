node {
   def mvnHome
   stage('Build and unit tests') { // for display purposes
     sleep 2
   }
   stage('Integration-tests') { // for display purposes
     sleep 2
   }
   stage('Acceptance-tests') {
       parallel (
        chrome: { sh "sleep 2s;" },
        edge: { sh "sleep 2s;" },
        firefox: { sh "sleep 2s;" }
       )
   }
   stage('Staging') {
        sleep 2
   }
   stage('Manual-approval') {
      input 'Deploy in Production'
   }
    stage('Deploy') {
        sleep 2
    }
}
