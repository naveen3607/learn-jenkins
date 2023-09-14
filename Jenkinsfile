/* pipeline {
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

     triggers { pollSCM('*//*  *//* 1 * * * *') }

     tools {
         maven 'maven'
     }

    stages {
        stage('Compile') {
            input {
                message "Should I Continue?"
                ok "Yes, you should."
            }

            when {
                branch 'production'
            }

            steps {
                //echo 'Hello World'
                //error 'This is an error'
                echo Test_URL
                echo SSH
                sh 'env'
                sh 'ansible -i 172.31.92.19, all -e ansible_user=${SSH_USR} -e ansible_password=${SSH_PSW} -m ping'
                sh 'mvn --version'
            }
        }
    }

    post {
        always {
          echo 'post'
        }
    }
} */

pipeline {
    agent any
    stages {
        stage('Non-Parallel Stage') {
            steps {
                echo 'This stage will be executed first.'
            }
        }
        stage('Parallel Stage') {
            when {
                branch 'master'
            }
            failFast true
            parallel {
                stage('Branch A') {
                    agent {
                        label "for-branch-a"
                    }
                    steps {
                        echo "On Branch A"
                    }
                }
                stage('Branch B') {
                    agent {
                        label "for-branch-b"
                    }
                    steps {
                        echo "On Branch B"
                    }
                }
                stage('Branch C') {
                    agent {
                        label "for-branch-c"
                    }
                    stages {
                        stage('Nested 1') {
                            steps {
                                echo "In stage Nested 1 within Branch C"
                            }
                        }
                        stage('Nested 2') {
                            steps {
                                echo "In stage Nested 2 within Branch C"
                            }
                        }
                    }
                }
            }
        }
    }
}
