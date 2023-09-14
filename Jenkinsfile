pipeline {
    agent { node { label 'workstation' } }
    environment {
        Test_URL = "google.com"
        SSH = credentials("centos-ssh")
    }

    options {
        ansiColor('xterm')
    }

    stages {
        stage('Compile') {
            steps {
                //echo 'Hello World'
                //error 'This is an error'
                echo Test_URL
                echo SSH
                sh 'env'
                sh 'ansible -i 172.31.92.19, all -e ansible_user=${SSH_USR} -e ansible_password=${SSH_PSW} -m ping'
            }
        }
    }

    post {
        always {
          echo 'post'
        }
    }
}
