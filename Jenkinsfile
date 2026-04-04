pipeline{
	agent{
		label "built-in"
	}
	stages{
		stage("Build war"){
			steps{
				sh'''
				mvn clean install
				'''
			}
		}
	}
}
