pipeline {
  agent any
  stages {
    stage('Update Test') {
      steps {
        parallel(
          "UPD1 Test": {
            echo 'UPD1 Installation Test Starting'
            
          },
          "UPD2 Test": {
            echo 'UPD2  Installation Test Starting'
            
          },
          "UPD3 Test": {
            echo 'UPD3  Installation Test Starting'
            
          }
        )
      }
    }
  }
}