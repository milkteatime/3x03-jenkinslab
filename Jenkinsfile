pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
        stage('OWASP Dependency Check') {
            steps {
                dependencyCheck additionalArguments: '--format HTML --format XML --disableYarnAudit', odcInstallation: 'dependency-check'
            }
        }
    // post {
    //     success {
    //         dependencyCheckPublisher pattern: 'dependency-check-report.xml'
    //     }
    //     }
    }
}
