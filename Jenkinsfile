pipeline {
    agent none 
    stages {
        stage('Build') { 
            agent {
                node {
			checkout scm

			docker.withRegistry('https://registry.hub.docker.com', 'docker') {
			image = docker.image('python:2-alpine')
			image.pull()
                }
            }
}
            steps {
                sh 'python -m py_compile sources/add2vals.py sources/calc.py' 
            }
        }
    }
}
