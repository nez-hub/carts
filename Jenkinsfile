pipeline{
	agent any
	
	tools{
		maven 'Maven 3.8.2'
	}

	stages {
		stage('build') {
			steps {
			echo 'Building...'
			sh 'mvn clean compile'
			}
		}
		stage('test') {
			steps {
			echo 'Testing...'
			sh 'mvn test'
			}
		}
		stage('package') {
			steps {
			echo 'Packaging...'
			sh 'mvn -DskipTests package'
			archiveArtifacts artifacts: '**/target/*.jar', fingerprint: true
			}
		}
	}
}

