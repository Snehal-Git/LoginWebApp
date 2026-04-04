pipeline{
	agent{
		label "built-in"
	}
	stages{
		stage("Build war"){
			steps{
				sh'''
				sudo mvn clean install
				'''
			}
		}
	}
}
