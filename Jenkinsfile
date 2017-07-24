pipeline {
  agent any
  stages {
    stage('UPD1') {
      steps {
        parallel(
          "UPD1": {
            echo 'UPD1 Installation Test Starting'
            sleep 30
            
          },
          "UPD2": {
            node(label: 'node2') {
              echo 'echo UPD1'
            }
            
            
          }
        )
      }
    }
    stage('UPD2') {
      steps {
        echo 'UPD2 Installation Test Starting'
        sleep 20
      }
    }
    stage('UPD3') {
      steps {
        echo 'UPD3 Installation Test Starting'
        sleep 10
      }
    }
    stage('Publish Results') {
      steps {
        echo 'Publishing results'
      }
    }
  }
}