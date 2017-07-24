pipeline {
  agent any
  stages {
    stage('Update Test') {
      steps {
        parallel(
          "Update Test": {
            echo 'Hello UPD1'
            
          },
          "UPD2 Test": {
            echo 'UPD2'
            
          },
          "UPD3 Test": {
            echo 'UPD3'
            
          }
        )
      }
    }
  }
}