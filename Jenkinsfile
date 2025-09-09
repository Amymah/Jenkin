pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'master', url: 'https://github.com/Amymah/Jenkin.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                // If you have requirements.txt in repo
                // bat 'pip install -r requirements.txt'

                // Or install specific packages directly (example: selenium, pandas)
                bat 'pip install selenium pandas'
            }
        }

        stage('Run Python Files') {
            steps {
                bat 'python Instance_Static_methods.py'
                bat 'python Local_Global_Variables.py'
            }
        }
    }
}
