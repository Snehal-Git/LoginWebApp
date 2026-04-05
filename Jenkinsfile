
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
				label "Slave-1"
			}
			steps{
				echo "slave"
			}
		}
	}
}
