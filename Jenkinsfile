pipeline {
  agent any
  stages {
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
    stage('build') {
      steps {
        sh '''#!/usr/bin/env bash
set -ex

cat some-text-file.log
'''
      }
    }
  }
}