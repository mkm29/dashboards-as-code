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
        sh(returnStdout: true, script: '''#!/bin/bash
            for $file in `git diff --name-only ${GIT_PREVIOUS_SUCCESSFUL_COMMIT} ${GIT_COMMIT}`; do
            if [ $file == *.json ];then
            echo ""Uploading $file"
            else
            echo "Skipping file $file"
            fi
            done
        '''.stripIndent())
      }
    }
  }
}