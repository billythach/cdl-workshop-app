node {
   def mvnHome
   stage('Build and unit tests') { // for display purposes
     checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: 'd8820f20-d415-44ef-92c2-7287477c092f', url: 'https://github.com/mpailloncy/cdl-workshop-app.git']]])   
   }
   stage('Integration-tests') { // for display purposes
     sleep 1
   }
   stage('Acceptance-tests') {
       parallel (
        chrome: { sh "sleep 2s;" },
        edge: { sh "sleep 2s;" },
        firefox: { sh "sleep 2s;" }
       )
   }
   stage('Staging') {
        sleep 1
   }
   stage('Manual-approval') {
      input 'Deploy in Production'
   }
    stage('Deploy') {
        sleep 1
    }
}
