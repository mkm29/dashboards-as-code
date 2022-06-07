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
        sh '''
        files=`git diff --name-only ${GIT_PREVIOUS_SUCCESSFUL_COMMIT} ${GIT_COMMIT}`
        # loop over all JSON files in files
        for file in $files; do
          # if file is a JSON file
          if [[ $file == *.json ]]; then
            upload_file $file
          fi
        done
        '''
      }
    }
  }
}