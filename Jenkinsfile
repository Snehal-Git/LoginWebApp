pipeline{
	agent{
		label "built-in"
	}
	tools {
        maven 'apache-maven-3.9.14'
    }
	stages{
		stage("Build war"){
			steps{
				sh "mvn clean install"
			}
		}
		stage("Create s3"){
			steps{
				sh'''
				aws s3 mb s3://snehal-assignment-15
				'''
			}
		}
		stage("Copy to s3"){
			steps{
				sh '''
				aws s3 cp /var/lib/jenkins/workspace/Assignment-15/target/LoginWebApp.war s3://snehal-assignment-15/
				'''
			}
		}
	}
}
