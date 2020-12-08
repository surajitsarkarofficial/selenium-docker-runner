pipeline{

	agent any
	stages{
		stage('Grid Up')
		{
			steps{
				bat "docker-compose up -d hub firefox chrome"
			}
		}
		stage('Test Run')
		{
			steps{
				bat "docker-compose up flights-chrome flights-firefox"
			}
		}
	}
	post{
		always{
			archiveArtifacts artifacts: "output/**"
			bat "docker-compose down"
		}
	}

}