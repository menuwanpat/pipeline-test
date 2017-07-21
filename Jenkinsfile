pipeline {
  agent any
  stages {
    stage('Initialize') {
      steps {
        echo 'Starting Client Sync Build'
        svn 'http://cmbsvn01/svn/ifsapp/projects/core-9.0/builds/sync-client'
      }
    }
  }
}