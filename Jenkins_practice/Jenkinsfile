pipeline {
    agent any
    
    stages {
        stage('Update and Install Packages') {
            steps {
                bat 'choco install python3'
                bat 'pip install mlflow torchvision>=0.15.1 torch>=2.0 lightning==2.0.0'
            }
        }
        
        stage('Run Python Script') {
            steps {
                bat 'python main.py'
            }
        }
    }
    
    post {
        always {
            echo 'Pipeline completed.'
        }
    }
}
