pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                git branch: 'main', url: 'https://github.com/mdzafaruddin-linux/simple-html-project.git'
            }
        }

        stage('Build') {
            steps {
                sh '''
                    mkdir -p build
                    cp index.html build/
                '''
            }
        }

        stage('Publish HTML Report') {
            steps {
                publishHTML(target: [
                    allowMissing: false,
                    alwaysLinkToLastBuild: true,
                    keepAll: true,
                    reportDir: 'build',
                    reportFiles: 'index.html',
                    reportName: 'HTML Report'
                ])
            }
        }
    }
}
