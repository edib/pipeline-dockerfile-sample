pipeline {
  agent {
    dockerfile true
  }
  stages {
    stage('Example') {
      steps {
        echo 'Hello World!'
        sh 'echo myCustomEnvVar = $myCustomEnvVar'
      }
    }
  stage('Push') {
    steps {
      script {
        
          docker.withServer('tcp://docker:2376') {
        docker.withRegistry('http://172.18.0.4:5000') {

        docker.image('my-ubuntu').inside {
            sh 'env'
        }
    }
            
      }
    }
    }
  }
}
