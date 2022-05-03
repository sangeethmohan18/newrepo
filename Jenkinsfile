pipeline{

	agent { label 'slave1'}

	stages {
		
		stage('Build') {
			
			steps {

				echo ("Build successful")

				   }
						}
				   
		stage('Test') {

			steps {

				echo ("Testing successful")
				  
				  }
				  	
				  	   }


        stage('Deploy') {

        	steps {

        		echo ("Deployment Successful")

        		  }

        		  		}




                          

		stage(' slacknotification') {

			steps {

				slackSend channel: '#jen-slackintegration', message: 'Build successful'

				  }

									}





			}
	
}












	


























