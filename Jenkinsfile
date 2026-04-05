
pipeline{
	agent{
		label "Slave-1"
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
		stage("Deploy to slave"){
			steps{
				sh '''
				cp /mnt/jenkins-slave/workspace/Assignment-20/target/LoginWebApp.war /mnt/servers/apache-tomcat-11.0.21/webapps/
				'''
			}
		}
	}
}
