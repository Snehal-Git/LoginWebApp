
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
				echo "Hi"
			}
		}

	}
}
