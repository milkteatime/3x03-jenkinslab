pipeline {
	agent any
	stages {
		// stage('Checkout SCM') {
		// 	steps {
		// 		git '/home/JenkinsDependencyCheckTest'
		// 	}
		// }

		stage('OWASP DependencyCheck') {
			steps {
				dependencyCheck additionalArguments: '--format HTML --format XML --suppression Jenkins/DependencyCheckTest/suppression.xml --disableYarnAudit', odcInstallation: 'dependency-check'			}
		}
	}	
	post {
		success {
			dependencyCheckPublisher pattern: 'dependency-check-report.xml'
		}
	}
}