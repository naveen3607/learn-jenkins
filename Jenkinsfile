pipeline {
    agent { node { label 'workstation' } }
    environment {
        Test_URL = "google.com"
        SSH = credentials("centos-ssh")
    }

    options {
        ansiColor('xterm')
    }

     parameters {
            string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')

            text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')

            booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')

            choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')

            password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
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
