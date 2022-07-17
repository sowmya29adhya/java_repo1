pipeline{
    agent {label 'slave1'}
	stages{
        stage('git checkout'){
            steps{
			    git 'https://github.com/sowmya29adhya/java_repo1.git'
                echo "checkout successfull"
            }
        }
		
		stage('build'){
			steps{
				sh 'mvn clean install'
				echo "build is successfull"
			}			
		}
			
		stage('push to artifactory'){
			steps{
				echo "push stage is successfull"
			}				
		}
		stage('deploy'){
			steps{
				sh 'sudo cp /home/ec2-user/jenkins/workspace/cicd-pipeline/target/*.war /opt/tomcat/webapps'
				echo "deployment is successfull"
			}				
		}
	}
}
