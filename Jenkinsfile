
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
			steps{
				sh '''
				aws s3 cp /var/lib/jenkins/workspace/Assignment-19.b/target/LoginWebApp.war s3://snehal-assignment-19.b
				'''
			}
		}

	}
}
