pipeline {
    agent any

    stages {
        stage('Check Python in Jenkins') {
            steps {
                // Check if Python is available to Jenkins
                bat 'where python'
                bat 'python --version'
            }
        }

        stage('Install Dependencies') {
            steps {
                // Install the required Python libraries
                bat 'pip install selenium pandas'
            }
        }

        stage('Run Python Files') {
            steps {
                // Run your Python scripts
                bat 'python Instance_Static_methods.py'
                bat 'python Local_Global_Variables.py'
            }
        }
    }
}
