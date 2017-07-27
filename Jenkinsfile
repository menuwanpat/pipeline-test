pipeline {
  agent {
    node {
      label 'master'
    }
    
  }
  stages {
    stage ('Initialize') {
      steps {
        echo 'Initializing....'
      }
    }
    stage('Run Update Installation Test') {
      steps {
        parallel(
          "APP9 UPD1": {
            node(label: 'slave_02') {
              withEnv(['UPD_VALUE=1']) {
                ws('D:\\ifs\\UPD_IT\\scripts') {
                  echo "START Create APP9 UPD${UPD_VALUE} Base Environment"
                  bat 'call CloneDatabase\\Clonedatabase.cmd'
                  bat 'call CopyBuildHome\\CopyBuildHome.cmd'
                  bat 'call CopyComponents\\CopyComponents.cmd'
                  bat 'call CloneIFSHome\\CloneIFSHome.cmd'
                  echo "STOP Create APP9 UPD${UPD_VALUE} Base Environment"
                }
              }
            }
            
            
          },
          "APP9 UPD2": {
            node(label: 'slave_01') {
              withEnv(['UPD_VALUE=2']) {
                echo "START Create APP9 UPD${UPD_VALUE} Base Environment"
                sleep 10
                echo "STOP Create APP9 UPD${UPD_VALUE} Base Environment"
              }
            }
            
            
          },
          "APP9 UPD3": {
            node(label: 'slave_01') {
              withEnv(['UPD_VALUE=3']) {
                echo "START Create APP9 UPD${UPD_VALUE} Base Environment"
                sleep 10
                echo "STOP Create APP9 UPD${UPD_VALUE} Base Environment"
              }
            }
            
            
          },
          "APP9 UPD4": {
            node(label: 'slave_02') {
              withEnv(['UPD_VALUE=4']) {
                echo "START Create APP9 UPD${UPD_VALUE} Base Environment"
                sleep 10
                echo "STOP Create APP9 UPD${UPD_VALUE} Base Environment"
              }
            }
            
            sleep 15
            
          },
          "APP9 UPD5": {
            node(label: 'slave_02') {
              withEnv(['UPD_VALUE=5']) {
                echo "START Create APP9 UPD${UPD_VALUE} Base Environment"
                sleep 10
                echo "STOP Create APP9 UPD${UPD_VALUE} Base Environment"
              }
            }
            
            
          },
          "APP9 UPD6": {
            node(label: 'slave_02') {
              withEnv(['UPD_VALUE=6']) {
                ws('D:\\ifs\\UPD_IT\\scripts') {
                echo "START Create APP9 UPD${UPD_VALUE} Base Environment"
                  bat 'call CloneDatabase\\Clonedatabase.cmd'
                  bat 'call CloneIFSHome\\CloneIFSHome.cmd'
                  bat 'call CopyBuildHome\\CopyBuildHome.cmd'
                  bat 'call CopyComponents\\CopyComponents.cmd'
                  echo "STOP Create APP9 UPD${UPD_VALUE} Base Environment"
                }
              }
            }
            
            
          },
          "APP9 UPD7": {
            node(label: 'slave_02') {
              withEnv(['UPD_VALUE=7']) {
                echo "START Create APP9 UPD${UPD_VALUE} Base Environment"
                sleep 10
                echo "STOP Create APP9 UPD${UPD_VALUE} Base Environment"
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
