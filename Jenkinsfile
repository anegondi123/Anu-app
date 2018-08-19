node{
   stage('SCM Checkout'){
     git 'https://github.com/anegondi123/anu-app'
   }
   stage('Compile-Package'){
      // Get maven home path
      def mvnHome =  tool name: 'maven-3', type: 'maven'   
      sh "${mvnHome}/bin/mvn package"
   }
   stage('Email Notification'){
      mail bcc: '', body: '''Hi Welcome to jenkins email alerts
      Thanks
      Ramesh''', cc: '', from: '', replyTo: '', subject: 'Jenkins Job', to: 'ram.anegondi@gmail.com'
   }
   stage('Slack Notification'){
       slackSend baseUrl: 'https://hooks.slack.com/services/',
       channel: '#jenkins-pipeline-demo',
       color: 'good', 
       message: 'Welcome to Jenkins, Slack!', 
       teamDomain: 'anucloud',
       tokenCredentialId: 'slack-demo'
   }
}
