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
        dir('D:\\ifs\\SYNC_Pipleline\\Client\\Pub') {
        bat "\"${tool 'MSBuild_40'}\" .\Checkout\fndbas\source\default.build /P:Languages=en /FL /FLP:LogFile=.\Logs\CompileClient\CompileClient.log;Verbosity=normal" && exit %ERRORLEVEL%
      }        
    }
  }
}
