pipeline{
	agent any
	stages{
	stage('checkout'){
	steps{
	echo "Cloning repo"
	git url:"https://github.com/Akshithareddyk/week7.git",
	branch:'main'
	}
	}
	stage('Build'){
	steps{
	echo "Build Docker Image"
	sh "docker build -t mywebapp ."
	}
	}
	stage('Run'){
	steps{
	echo "Run application in Docker Container"
	sh "docker rm -f mycontainer || exit 0"
	sh "docker run -d -p 5001:5001 --name mycontainer mywebapp"
	}
	}
	}
	post{
	success{
	echo 'Pipeline finished successfully!'
	}
	failure{
	echo 'Pipeline failed.Please check the logs'
	}
	
	}
}
