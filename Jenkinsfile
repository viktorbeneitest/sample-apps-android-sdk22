pipeline {
  agent any
  stages {
    stage('test') {
      steps {
        sh '''#!/usr/bin/env bash
set -ex

uname -a
sleep 10
ls -alh
'''
      }
    }
  }
}
