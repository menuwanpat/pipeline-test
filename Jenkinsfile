pipeline {
  agent any
  stages {
    stage('UPD1') {
      steps {
        parallel(
          "UPD1": {
            node(label: 'node1') {
              echo 'echo UPD1'
              sleep 15
            }
            
            
          },
          "UPD2": {
            node(label: 'node2') {
              echo 'echo UPD2'
              sleep 10
            }
            
            
          },
          "UPD3": {
            node(label: 'node1') {
              echo 'UPD3'
              sleep 20
            }
            
            
          }
        )
      }
    }
    stage('Publish Results') {
      steps {
        echo 'Publishing results'
      }
    }
  }
}