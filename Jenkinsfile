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
			writeFile file: '/Dockerfile', text: 'RUN echo  "<BuilderName>Omar Bazaid</BuilderName>" >> /Manifest.txt'
		}
	}

	}
   stage('BuildDockerfile') {
            steps {
		sh "docker build --tag omar:/${BUILD_NUMBER ./}"
            }
        }
        }

        
        
agent any
    stages {
        stage('Build') {
            steps {
                sh 'ls -lh && cat Dockerfile && cat Mainfest.txt && docker images'
                sh 'docker ps -a'
                //sh 'docker build -t abdul-image .'
                echo 'Building..'
             
            }
        }
        
        // stage 2
        stage('Deploy') {
            steps {
                echo 'Deploying..'
                //sh 'docker run -p 8080:8080 -p 50000:50000 -v jenkins_home_abdul:/var/jenkins_home -d abdul-image '
                //sh 'docker rename jovial_yalow bryan-abdul:23' failed to rename 
                sh 'docker ps -a'
             }
        }
        
        stage('ValidateStageDeployment') {
            steps {
                echo 'validate deployment on staging....'
            }
        }
    }
}
