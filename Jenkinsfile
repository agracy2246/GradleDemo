pipeline {
    agent {
        label 'demo-slave'
    }
    stages {
        stage('Build') {
            steps {
                sh './gradlew build'

                    // publish html
                publishHTML target: [
                    allowMissing: false,
                    alwaysLinkToLastBuild: false,
                    keepAll: true,
                    reportDir: 'coverage',
                    reportFiles: 'index.html',
                    reportName: 'RCov Report'
                ]
            }

        
        }
        stage('Test') {
            steps {
                sh './gradlew test'
            }
        }
        
    }
}
