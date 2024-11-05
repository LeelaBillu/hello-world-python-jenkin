pipeline {
    agent any

    stages {
        // Stage 1: Checkout Code from GitHub
        stage('Checkout') {
            steps {
                git url: 'https://github.com/LeelaBillu/hello-world-python-jenkin', branch: 'main'
                echo 'checkouted'
            }
        }

       // Stage 2: Run hello.py script
        stage('Run Hello Script') {
            steps {
                script {
                    // Execute the hello.py script
                    bat 'python hello.py'  // Use 'python3 hello.py' if your system uses Python 3.x
                }
            }
        stage('Run Test cases'){
            steps{
                bat 'python test_hello.py'
       }
    }

    post {
        always {
            echo 'Build finished'
        }
    }
}
