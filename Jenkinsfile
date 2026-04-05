
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
		stage("Deploy on Slave"){
			agent{
				label{
					label "Slave-1"
				}
			}
			steps{
				sh '''
				scp -o StrictHostKeyChecking=no \
/var/lib/jenkins/workspace/Assignment-16/target/LoginWebApp.war \
ec2-user@172.31.35.32:/mnt/servers/apache-tomcat-11.0.21/webapps/
				'''
			}
		}
	}
}
