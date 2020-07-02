node {
	def app

	stage('Clone repo') {
		checkout scm
	}
	
	stage('Build image') {
		app = docker.build('st1ngrayone/example-app')
	}

	stage('Push image') {

        docker.withRegistry('https://registry.hub.docker.com', 'docker-hub-credentials') {
            app.push("latest")
        }
    }	
}
