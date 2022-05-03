pipeline {

	agent { label 'slave1'}
	
	stages {

		stage ('Build stage') {

			steps {

				slackSend channel: 'jen-slackintegration', message: 'Build started: ${env.JOB_NAME} ${env.BUILD_ID}'

				sh "mvn -B -DskipTests clean package"
                   }
            post {

            	success {

            		slackSend channel: 'jen-slackintegration', message: 'Build completed successfully: ${env.JOB_NAME} ${env.BUILD_ID}'
            	}
            
            	failure {


            		slackSend channel: 'jen-slackintegration', message: 'Build failed: ${env.JOB_NAME} ${env.BUILD_ID}'



            	}


            }	



            }       


		                      
		stage('Testing') {
		
			steps {


				sh "mvn test"

				  }

			post {
			
				always{

					junit 'target/surefire-reports/*.xml'


   						}	  
   				
   				success {
   				
   					slackSend channel: 'jen-slackintegration', message: 'Build completed successfully: ${env.JOB_NAME} ${env.BUILD_ID}'	

   				}		

   				failure {

   					slackSend channel: 'jen-slackintegration', message: 'Build failed: ${env.JOB_NAME} ${env.BUILD_ID}'		

   				}

               	}



                           }   

            stage('Archive artifact') {
            

            	steps {

            		archiveArtifacts artifacts: 'samplejava/target/*.jar', followSymlinks: false


            	}
            }                                





	}
}
