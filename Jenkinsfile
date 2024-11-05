pipeline {
    agent any

    stages {
        // Stage 1: Checkout Code from GitHub
        stage('Checkout') {
            steps {
                git url: 'https://github.com/LeelaBillu/hello-world-python-jenkin.git', branch: 'main'
                echo 'checkouted'
            }
        }

        // Stage 2: Run hello.py script
        // stage('Run Hello Script') {
        //     steps {
        //         script {
        //             // Execute the hello.py script
        //             sh 'python hello.py'  // Use 'python3 hello.py' if your system uses Python 3.x
        //         }
        //     }
        }
    }

    post {
        always {
            echo 'Build finished'
        }
    }
}
