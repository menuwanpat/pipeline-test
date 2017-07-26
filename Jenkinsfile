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
                  echo 'START Create UPD%UPD_VALUE% Base Environment'
                  bat 'call CloneDatabase\\Clonedatabase.cmd'
                  bat 'call CloneIFSHome\\CloneIFSHome.cmd'
                  echo 'END Create UPD%UPD_VALUE% Base Environment'
                }
              }
            }
            
            
          },
          "UPD2": {
            node(label: 'slave_01') {
              withEnv(['UPD_VALUE=2']) {
                echo 'START Create UPD%UPD_VALUE% Base Environment'
                sleep 10
                echo 'END Create UPD%UPD_VALUE% Base Environment'
              }
            }
            
            
          },
          "UPD3": {
            node(label: 'slave_01') {
              withEnv(['UPD_VALUE=3']) {
                echo 'START Create UPD%UPD_VALUE% Base Environment'
                sleep 10
                echo 'END Create UPD%UPD_VALUE% Base Environment'
              }
            }
            
            
          },
          "UPD4": {
            node(label: 'slave_02') {
              withEnv(['UPD_VALUE=4']) {
                echo 'START Create UPD%UPD_VALUE% Base Environment'
                sleep 10
                echo 'END Create UPD%UPD_VALUE% Base Environment'
              }
            }
            
            sleep 15
            
          },
          "UPD5": {
            node(label: 'slave_02') {
              withEnv(['UPD_VALUE=5']) {
                echo 'START Create UPD%UPD_VALUE% Base Environment'
                sleep 10
                echo 'END Create UPD%UPD_VALUE% Base Environment'
              }
            }
            
            
          },
          "UPD6": {
            node(label: 'slave_02') {
              withEnv(['UPD_VALUE=6']) {
                ws('D:\\ifs\\UPD_IT\\scripts') {
                  echo 'START Create UPD%UPD_VALUE% Base Environment'
                  bat 'call CloneDatabase\\Clonedatabase.cmd'
                  bat 'call CloneIFSHome\\CloneIFSHome.cmd'
                  echo 'END Create UPD%UPD_VALUE% Base Environment'
                }
              }
            }
            
            
          },
          "UPD7": {
            node(label: 'slave_02') {
              withEnv(['UPD_VALUE=7']) {
                echo 'START Create UPD%UPD_VALUE% Base Environment'
                sleep 10
                echo 'END Create UPD%UPD_VALUE% Base Environment'
              }
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
