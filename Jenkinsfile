pipeline {
    agent { node { label 'workstation' } }
    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
                error 'This is an error'
            }
        }
    }
}
