throttle(['throttleDocker']) {
  node('docker') {
    wrap([$class: 'AnsiColorBuildWrapper']) {
      try{
        stage('Clone repo'){
          checkout scm
        }
        stage('Build Image'){
          sh '''
            echo $SERVER_IP swarm | sudo tee -a /etc/hosts
          '''
          docker.withServer('tcp://swarm:2376', 'dockerswarm'){
					  docker.image('mysql:5').withRun('-p 3306:3306') {
					  /* do things */
					  }
          }
        }
      }
    }
  }
}
