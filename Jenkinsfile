pipeline {
  
    agent { docker { image 'bryandollery/terraform-packer-aws-alpine' } }
    options {
        skipStagesAfterUnstable()
    }
    stages {
    stage('CreateDockerFile'){
	    steps {
		script {
			writeFile file: '/Dockerfile', text: 'FROM bryandollery/terraform-packer-aws-alpine'
			writeFile file: '/Dockerfile', text: 'RUN echo  "<BuilderName>Nuha Baghanim</BuilderName>" >> /Manifest.txt'
		}
	}

	}
   stage('BuildDockerfile') {
            steps {
		sh "docker build --tag Nuha:/${BUILD_NUMBER ./}"
            }
        }
        }
    }
  
