pipeline{

	agent any

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




            }              

		stage(' slacknotification') {

			steps {

				slackSend channel: '#jenkins-slack', message: 'Build successful'

				  }

									}





			}












	


























