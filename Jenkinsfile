node('workstation') {
  def x:integer = 10
  env.y = 20
  stage('Test') {
    print x
    sh 'echo y - ${y}'
  }
}

