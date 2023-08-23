pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Checkout your repository
                // For example:
                git branch: 'main', url: 'https://github.com/sarthakd112/myrepo'
            }
        }
        
        stage('Run Python Script') {
            steps {
                // Run your Python script here
                // Adjust the path to your main.py if necessary
                bat '/main.py'
            }
        }

        stage('Display Console Output') {
            steps {
                script {
                    // Read and print the contents of the console log
                    def consoleLog = currentBuild.rawBuild.getLog(1000)
                    echo consoleLog
                }
            }
        }
    }

    post {
        always {
            // Clean up or perform other tasks after the build
            // For example:
            // bat 'cleanup_command_here'
        }
    }
}
