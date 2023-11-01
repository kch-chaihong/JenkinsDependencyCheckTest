pipeline {
	agent any
	stages {
		stage('Checkout SCM') {
			steps {
				// git '/home/JenkinsDependencyCheckTest'
        git url: 'https://github.com/YanRongLee/JenkinsDependencyCheckTest.git'
			}
		}

		stage('OWASP DependencyCheck') {
			steps {
				dependencyCheck additionalArguments: '--format HTML --format XML', odcInstallation: 'OWASP Dependency-Check Vulnerabilities'
			}
		}
	}	
	post {
		success {
			dependencyCheckPublisher pattern: 'dependency-check-report.xml'
		}
	}
}
