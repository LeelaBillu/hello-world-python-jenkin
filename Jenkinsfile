pipeline {
    agent any

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
        // Notify on success
        success {
            echo 'Build sucess'
            mail to: 'leelakumaryadav123@gmail.com',
                 subject: "Build success: ${currentBuild.fullDisplayName}",
                 body: "The build has failed.\n\nYou can check the details here : ${env.BUILD_URL}"
        }

        // // Notify on failure
        // failure {
        //     echo 'Build failed.'
        //     mail to: 'leelakumaryadav123@gmail.com',
        //          subject: "Build Failure",
        //          body: "The build has failed.\n\nYou can check the details"
        // }

        // // Always notify (optional)
        // always {
        //     echo 'Build finished'
        //     // This is where you could send a notification regardless of success or failure
        //     mail to: 'leelakumaryadav123@gmail.com',
        //          subject: "Build Finished: ",
        //          body: "The build has finished.\n\nYou can check the details"
        // }
    }
}
