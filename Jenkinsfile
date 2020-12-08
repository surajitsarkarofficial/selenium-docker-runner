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
		stage('Bring Grid Down')
		{
			steps{
				bat "docker-compose down"
			}
		}
	}

}