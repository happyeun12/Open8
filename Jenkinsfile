node{
	def app
	stage('Clone repository'){
		git 'https://github.com/happyeun12/Open8.git'
	}
	stage('Build image'){
		app = docker.build("eunjinchoi11/test")
	}
	stage('Test image'){
		app.inside{
			sh 'make test'
		}
	}
	stage('Push image'){
		docker.withRegistry('https://registry.hub.docker.com', 'eunjinchoi11')}
		 	app.push("{env.BUILD_NUMBER}")
			app.push("latest")
		}
	}
}
