pipeline {
    agent { label 'windows-label' } 

    stages {
        // Stage 1: Checkout Code from GitHub
        stage('Checkout') {
            steps {
                git url: 'https://github.com/LeelaBillu/hello-world-python-jenkin', branch: 'main'
                echo 'Checked out code from GitHub'
            }
        }

        // Stage 2: Install Dependencies
        stage('Install Dependencies') {
            steps {
                bat 'pip install pytest'  // Use 'pip3 install pytest' if using Python 3.x
            }
        }

        // Stage 3: Run hello.py script
        stage('Run Hello Script') {
            steps {
                script {
                    // Execute the hello.py script
                    bat 'python hello.py'  // Use 'python3 hello.py' if using Python 3.x
                }
            }
        }

        // Stage 4: Run Test Cases
        stage('Run Test cases') {
            steps {
                bat 'python test_hello.py'  // Use 'python3 test_hello.py' if using Python 3.x
            }
        }
    }

   post {
    success {
        echo 'Build success'
        echo "Build result: ${currentBuild.result}" // Add this line for debugging
        mail to: 'vandana.kenche123@gmail.com',
             subject: "Build Success: ${currentBuild.fullDisplayName}",
             body: "The build was successful.\n\nYou can check the details here : ${env.BUILD_URL}"
    }
    failure {
        echo 'Build failed'
        echo "Build result: ${currentBuild.result}" // Add this line for debugging
        mail to: 'vandana.kenche123@gmail.com',
             subject: "Build Failed: ${currentBuild.fullDisplayName}",
             body: "The build has failed.\n\nYou can check the details here : ${env.BUILD_URL}"
    }
}

}
