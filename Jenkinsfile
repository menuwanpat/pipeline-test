pipeline {
  agent any
  stages {
    stage('Initialize') {
      steps {
        echo 'Intializing Client Sync Build'
        dir('D:\\ifs\\SYNC_Pipleline\\Client\\Pub') {
          checkout changelog: false, poll: false, scm: [$class: 'SubversionSCM', additionalCredentials: [[credentialsId: 'svncredentials', realm: '<http://cmbsvn01:80> SVN Repo']], excludedCommitMessages: '', excludedRegions: '', excludedRevprop: '', excludedUsers: '', filterChangelog: false, ignoreDirPropChanges: false, includedRegions: '', locations: [[credentialsId: 'svncredentials', depthOption: 'infinity', ignoreExternalsOption: false, local: 'Checkout', remote: 'http://cmbsvn01/svn/ifsapp/projects/core-9.0/builds/sync-client']], workspaceUpdater: [$class: 'UpdateUpdater']]
        }        
      }
    }
    stage('Build') {
      steps {
        echo 'Starting MSBuild'
      }        
    }
  }
}
