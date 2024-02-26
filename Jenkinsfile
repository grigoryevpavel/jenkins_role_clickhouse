pipeline {
    agent { label 'agent'}
    stages {
       stage('checkout'){
           steps{
               checkout scmGit(branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[credentialsId: 'jenkins', url: 'https://github.com/grigoryevpavel/jenkins_role_clickhouse']])
           }
       }
       stage('test'){
           steps{
               sh '''if [-d "molecule"]; then rm -R molecule; fi
molecule init scenario
molecule test'''
           }
       }
    }
}