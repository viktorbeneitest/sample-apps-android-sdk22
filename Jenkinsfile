pipeline {
  agent any
  stages {
    stage('test') {
      parallel {
        stage('test') {
          steps {
            sh '''#!/usr/bin/env bash
set -ex

uname -a
sleep 10
pwd
sleep 10
ls -alh > some-text-file.log
'''
            echo 'test msg'
            timeout(time: 10) {
              sleep 5
            }
            
          }
        }
        stage('parallel-test-step') {
          steps {
            sh '''echo \'parallel!!\'
sleep 10
echo \'dun\''''
          }
        }
      }
    }
    stage('build') {
      parallel {
        stage('build') {
          steps {
            sh '''#!/usr/bin/env bash
set -ex

cat some-text-file.log
'''
          }
        }
        stage('stg') {
          steps {
            pwd(tmp: true)
            input 'continue?'
          }
        }
      }
    }
    stage('finishing') {
      steps {
        sleep 30
        sh 'echo \'we are done!\''
      }
    }
  }
}
