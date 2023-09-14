pipeline {
    agent { node { label 'workstation' } }
    environment {
        Test_URL = "google.com"
        SSH = credentials("centos-ssh")
    }

    stages {
        stage('Compile') {
            steps {
                //echo 'Hello World'
                //error 'This is an error'
                echo Test_URL
                echo SSH
            }
        }
    }

    post {
        always {
          echo 'post'
        }
    }
}
