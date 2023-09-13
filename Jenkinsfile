pipeline {
    agent { node { label 'workstation' } }
    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
        stage('Test') {
            steps {
                echo 'Test'
            }
        }
        stage('Code Quality') {
            steps {
                echo 'Code Quality'
            }
        }
        stage('Code Security') {
            steps {
                echo 'Code Security'
            }
        }
        stage('App Deploy') {
            steps {
                echo 'App Deploy'
            }
        }
    }
}
