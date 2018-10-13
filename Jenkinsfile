pipeline {
  agent {
    docker {
      image 'node:8.12-alpine'
    }
  }

  triggers { pollSCM('H/2 * * * *') }

  stages {
    stage('Npm Build') {
      steps {
        sh 'npm run build'
      }
    }
  }

  post {
    success {
        echo 'I succeeeded!'
    }
    unstable {
        echo 'I am unstable :/'
    }
    failure {
        echo 'I failed :('
    }
  }
}

