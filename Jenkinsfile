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
            node(label: 'slave_02') {
              withEnv(['UPD_VALUE=1']) {
              ws('D:\\ifs\\UPD_IT\\scripts') {
                echo 'UPD1'
                bat 'call CloneDatabase\\Clonedatabase.cmd'
                echo 'Database Cloned.'
                bat 'call CloneDatabase\\CloneIFSHome.cmd'
                echo 'echo IFSHome Cloned.'
              }
              }
            }
            
            
          },
          "UPD2": {
            node(label: 'slave_01') {
              echo 'UPD2'
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
              echo 'UPD4'
            }
            
            sleep 15
            
          },
          "UPD5": {
            node(label: 'slave_02') {
              echo 'UPD5'
              sleep 10
            }
            
            
          },
          "UPD6": {
            node(label: 'slave_02') {
              withEnv(['UPD_VALUE=6']) {
              ws('D:\\ifs\\UPD_IT\\scripts') {
                echo 'UPD1'
                bat 'call CloneDatabase\\Clonedatabase.cmd'
                echo 'Database Cloned.'
                bat 'call CloneDatabase\\CloneIFSHome.cmd'
                echo 'echo IFSHome Cloned.'
              }
              }
            }
            
            
          },
          "UPD7": {
            node(label: 'slave_02') {
              echo 'UPD7'
              sleep 10
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
