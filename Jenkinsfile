def slackResponse = slackSend(channel: "#pipeline-Ynet", attachments: attachments)

pipeline {
    
    agent any
    
    stages{
        stage('Build the Code') {
            steps{
		script{
                sh "./gradlew build"
			}            
}
        }
	    
    }
}
