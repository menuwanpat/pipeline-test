pipeline {
  agent any
  stages {
    stage('Update Test') {
      steps {
        parallel(
          "UPD1 Test": {
            echo 'UPD1 Installation Test Starting'
            sleep 30
            bat 'bat / "echo %DATETIME%"'
            
          },
          "UPD2 Test": {
            echo 'UPD2  Installation Test Starting'
            sleep 20
            bat 'bat / "echo %DATETIME%"'
            
          },
          "UPD3 Test": {
            echo 'UPD3  Installation Test Starting'
            sleep 10
            bat 'bat / "echo %DATETIME%"'
            
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