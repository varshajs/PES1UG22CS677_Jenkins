pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                script {
                    // Make sure to specify the source file to compile, like PES1UG22CS677.cpp
                    sh 'g++ -o PES1UG22CS677 PES1UG22CS677.cpp' // Compile the C++ file to an executable
                }
            }
        }
        
        stage('Test') {
            steps {
                script {
                    // Run the compiled program
                    sh './PES1UG22CS677' // Run the executable
                }
            }
        }
        
        stage('Deploy') {
            steps {
                echo 'Deploying application...' 
                // Add deployment steps here if needed
            }
        }
    }
    
    post {
        failure {
            echo 'Pipeline failed! Please check the logs.'
        }
        success {
            echo 'Pipeline executed successfully!'
        }
    }
}

