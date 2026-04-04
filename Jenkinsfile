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
				aws s3 mb s3://snehal-assignment-15 2>/dev/null || true
				'''
			}
		}
		stage("Copy to s3"){
			steps{
				sh '''
				Date=$(date +"%Y%m%d-%H%M%S")
				mv /var/lib/jenkins/workspace/Assignment-15/target/LoginWebApp.war LoginWebApp-$Date.war
				aws s3 cp LoginWebApp-$Date.war s3://snehal-assignment-15
				'''
			}
		}
	}
}
