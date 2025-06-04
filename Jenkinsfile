pipeline{
	agent any
	tools{
		maven 'Maven'
	}
	stages{
		stage('Checkout'){
			steps{
				git branch:'master',url:'https://github.com/BPM2004/abhi.git'
			}
		}
		stage('Build'){
			steps{
				sh 'mvn clean package'
			}
		}
		stage('Test'){
			steps{
				sh 'mvn test'
			}
		}
		stage('Run Application'){
			steps{
				sh 'java -jar target/abhi-1.0-SNAPSHOT.jar'
			}
		}
	}
	post{
		success{
			echo 'Build success'
		}
		failure{
			echo 'Buils failed'
		}
	}
}
		
