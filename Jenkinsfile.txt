pipeline {
    agent any

    stages {
        stage('Verify Python Setup') {
            steps {
                echo 'Checking Python installation...'
                bat 'where python'
                bat 'python --version'
            }
        }

        stage('Install Dependencies') {
            steps {
                echo 'Installing required Python packages...'
                bat 'pip install selenium pandas'
            }
        }

        stage('Run Python Scripts') {
            steps {
                echo 'Executing Python scripts...'
                bat '''
                    python Instance_Static_methods.py
                    python Local_Global_Variables.py
                '''
            }
        }
    }

    post {
        always {
            echo 'Pipeline completed. Archiving logs if any...'
            archiveArtifacts artifacts: '**/*.txt', allowEmptyArchive: true
        }
        failure {
            echo 'Pipeline failed. Please check the logs for errors.'
        }
    }
}
