pipeline {
  agent { node { label 'workstation' } }

  environment {
    TEST_URL = "google.com"
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

  triggers { pollSCM('*/1 * * * *') }

  tools {
    maven 'maven'
  }

  stages {

    stage('Compile') {
      input {
        message "Should we continue?"
        ok "Yes, we should."
      }

      steps {
//        //echo 'Hello World'
//        //error 'This is an error'
        echo TEST_URL
        echo SSH
        sh 'env'
        sh 'ansible -i 172.31.85.208, all -e ansible_user=${SSH_USR} -e ansible_password=${SSH_PSW} -m ping'
        sh 'mvn version'
      }
    }
}

  post {
    always {
      echo 'Post'
    }
  }
}



node('workstation') {
  def x = 10
  env.y = 20
  stage('Test') {
    print x
    sh 'echo y - ${y}'
  }
}

