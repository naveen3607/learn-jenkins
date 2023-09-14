pipeline {
    agent { node { label 'workstation' } }
    environment {
        Test_URL = "google.com"
    }

    stages {
        stage('Compile') {
            steps {
                //echo 'Hello World'
                //error 'This is an error'
                echo Test_URL
            }
        }
    }

    post {
        always {
          echo 'post'
        }
    }
}
