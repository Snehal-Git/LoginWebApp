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
	}
}
