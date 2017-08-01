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
          "APP9 RTM": {
            node(label: 'slave_02') {
              withEnv(['UPD_VALUE=0', 'DB_SERVER=cmbpde1467']) {
                ws('D:\\ifs\\UPD_IT\\scripts') {
                echo "START Create APP9 UPD${UPD_VALUE} Base Environment"
                /* bat 'call Jenkins\\deleteShare.cmd'
                bat 'call CloneDatabase\\Clonedatabase.cmd'
                bat 'call CopyBuildHome\\CopyBuildHome.cmd'*/
                bat 'call CopyComponents\\CopyComponents.cmd'
                //bat 'call CloneIFSHome\\CloneIFSHome.cmd'
                echo "START installing delivery to APP9 UPD${UPD_VALUE} Base Environment"
                bat 'call BuildComponents\\BuildComponents.cmd && call jenkins\\waitOnErrors.cmd BuildComponents'
                bat 'call Build\\Build.cmd && call jenkins\\waitOnErrors.cmd Build'
                bat 'call PrepareDB\\PrepareDB.cmd && call jenkins\\waitOnErrors.cmd PrepareDB'
                bat 'call Install\\Install.cmd && call jenkins\\waitOnErrors.cmd Install'
                bat 'call PostDeployment\\PostDeployment.cmd'
                bat 'call AnalyzeDbErrors\\AnalyzeDbErrors.cmd'
                bat 'call ImportLangFiles\\ImportLangFiles.cmd && call jenkins\\waitOnErrors.cmd ImportLangFiles'
                bat 'call Jenkins\\createShare.cmd'
                echo "STOP Create APP9 UPD${UPD_VALUE} Base Environment"
                }
                ws('D:\\ifs\\UPD_IT\\Pub') {
                  cleanWs cleanWhenAborted: false, cleanWhenFailure: false, cleanWhenNotBuilt: false, cleanWhenSuccess: false, cleanWhenUnstable: false, patterns: [[pattern: 'Logs/**', type: 'INCLUDE'], [pattern: '', type: 'INCLUDE']]
                }
              }
            }
                        
          },
          "APP9 UPD1": {
            node(label: 'slave_02') {
              withEnv(['UPD_VALUE=1']) {
                ws('D:\\ifs\\UPD_IT\\scripts') {
                  echo "START Create APP9 UPD${UPD_VALUE} Base Environment"
                  //bat 'call Jenkins\\deleteShare.cmd'
                  //bat 'call CloneDatabase\\Clonedatabase.cmd'
                  //bat 'call CopyBuildHome\\CopyBuildHome.cmd'
                  //bat 'call CopyComponents\\CopyComponents.cmd'
                  //bat 'call CloneIFSHome\\CloneIFSHome.cmd'
                  //bat 'call Jenkins\\createShare.cmd'
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
                sleep 15
                echo "STOP Create APP9 UPD${UPD_VALUE} Base Environment"
              }
            }
            
            
          },
          "APP9 UPD6": {
            node(label: 'slave_02') {
              withEnv(['UPD_VALUE=6']) {
                ws('D:\\ifs\\UPD_IT\\scripts') {
                echo "START Create APP9 UPD${UPD_VALUE} Base Environment"
                  /*bat 'call Jenkins\\deleteShare.cmd'
                  bat 'call CloneDatabase\\Clonedatabase.cmd'
                  bat 'call CopyBuildHome\\CopyBuildHome.cmd'
                  bat 'call CopyComponents\\CopyComponents.cmd'
                  bat 'call CloneIFSHome\\CloneIFSHome.cmd'
                  bat 'call Jenkins\\createShare.cmd'*/
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
