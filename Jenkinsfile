pipeline{
	agent any
	stages{
		stage('Build'){
			steps{
				sh 'export PATH="/opt/apache-maven-3.5.2/bin:$PATH"'
				sh 'echo $PATH'
				sh 'mvn clean package'
			}
			post{
				success{
					echo 'Now Archiving...'
					archiveArtifacts artifacts: '**/target/*.war'
				}
			}
		}
	}
}
