
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
				echo "hi"
				'''
			}
		}
	}
}
