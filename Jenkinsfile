pipeline {
    agent { node { label 'workstation' } }
    stages {
        stage('Compile') {
            steps {
                echo 'Hello World'
                error 'This is an error'
            }
        }
    }

    post {
        always {
          echo 'post'
        }
    }
}
