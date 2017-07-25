pipeline {
  agent {
    node {
      label 'master'
    }
    
  }
  stages {
    stage('Update Installaion Test') {
      steps {
        parallel(
          "UPD1": {
            node(label: 'slave_01') {
              echo 'echo UPD1'
              sleep 15
            }
            
            
          },
          "UPD2": {
            node(label: 'slave_01') {
              echo 'echo UPD2'
              sleep 10
            }
            
            
          },
          "UPD3": {
            node(label: 'slave_01') {
              echo 'UPD3'
              sleep 20
            }
            
            
          },
          "UPD4": {
            node(label: 'slave_02') {
              echo 'ECHO installing UPD4'
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