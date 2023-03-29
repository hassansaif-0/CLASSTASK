pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                // Checkout code from repository
                checkout scm
            }
        }
        stage('Install Dependencies') {
            steps {
                // Install required Python packages
                bat 'python -m pip install --upgrade pip'
                bat 'pip install pylint'
                bat 'pip install black'
                bat 'pip install pytest'
                bat 'pip install -r requirements.txt
            }
        }
        stage('Format Code with Black') {
            steps {
                
                bat 'black main.py'
                
            }
        }
        stage('Analyse Code with Pylint') {
            steps {
                // Run Pylint on app.py
                bat 'pylint main.py'
               
            }
        }
       
    }
}
