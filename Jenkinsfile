def upload_file(file_name) {
  echo "Uploading $file_name"
}

pipeline {
  agent any

  stages {
    stage('Initialize') {
      steps {
        echo '****************************************************'
        sh 'env | grep -i git'
        // print out the current git branch
        echo '****************************************************'
        echo "Current git branch: ${GIT_BRANCH.split('/')[1]}"
        // branch is in GIT_BRANCH environment variable (eg origin/dev)
        echo '****************************************************'
        sh '''files=`git diff --name-only ${GIT_PREVIOUS_SUCCESSFUL_COMMIT} ${GIT_COMMIT} | grep json`
        for file in $files; do
        echo "Uploading $file"
        done
        '''
        sh(returnStdout: true, script: '''#!/bin/bash
            files=`git diff --name-only ${GIT_PREVIOUS_SUCCESSFUL_COMMIT} ${GIT_COMMIT} | grep json`
            echo "Changed files = $files"
            echo ****************************************************
            for file in $files; do
            echo "Uploading $file"
            done
        '''.stripIndent())
      }
    }
  }
}