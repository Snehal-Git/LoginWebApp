
pipeline{
	agent{
		label "built-in"
	}
	tools{
		maven 'apache-maven-3.9.14'
	}
	stages{
		stage ("Build war file"){
			steps{
				sh '''
				mvn clean install
				'''
			}
		}
		stage("Deploy to EC2"){
			agent{
				label{
					label "built-in"
				}
			}
			steps{
				sh '''
				scp /var/lib/jenkins/workspace/Assignment-19.a/target/LoginWebApp.war ec2-user@172.31.35.32:/mnt/servers/apache-tomcat-11.0.21/webapps/
				'''
			}
		}

	}
}
