pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                script {
                    // Intentional error: Trying to compile a non-existent file
                    sh 'g++ -o PES1UG22CS677 non_existent_file.cpp' // This will fail because the file does not exist
                }
            }
        }
        
        stage('Test') {
            steps {
                script {
                    // This stage will be skipped because the Build stage failed
                    sh './PES1UG22CS677' // Run the executable (will not be reached due to the error in Build)
                }
            }
        }
        
        stage('Deploy') {
            steps {
                echo 'Deploying application...' 
                // This stage will also be skipped due to the error in Build
            }
        }
    }
    
    post {
        failure {
            echo 'Pipeline failed! Please check the logs.' // This will be executed when the pipeline fails
        }
        success {
            echo 'Pipeline executed successfully!' // This will not be reached if the pipeline fails
        }
    }
}
