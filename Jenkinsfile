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
	
	    //no need to copy artifacts because we are using them here

	    //but if needed we could do that with the help of Jenkins 
	    
	    stage('Run the Application') {
		     steps{
		                    sh 'java -jar ./build/libs/Ynet-1.0-SNAPSHOT.jar &'
	         	  }
	                  	          }
    
	    stage('Slack'){
            	steps {
                slackSend(channel: slackResponse.channelId, message : 'Running Properly', timestamp: slackResponse.ts)
            	      }
        		  }   
	    
    }
}
