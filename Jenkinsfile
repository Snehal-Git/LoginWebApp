pipeline{
	agent{
		label "built-in"
	}
	tools{
		maven 'apache-maven-3.9.14'
	}
	stages{
		stage("Build war"){
			steps{
				sh '''
				mvn clean install
				'''
			}
		}
		stage("Deploy to EC2"){
			steps{
				scp /var/lib/jenkins/workspace/Assignment-16/target/LoginWebApp.war ec2-user@172.31.35.32:/root/servers/apache-tomcat-11.0.21/webapps
			}
		}
	}
}
