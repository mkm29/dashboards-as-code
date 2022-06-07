def UploadFile(String file_name) {
  echo "Uploading $file_name"
}

def GetBranch() {
  return ${GIT_BRANCH}.split('/')[1]
}

pipeline {
  agent any
  stages {
    stage('Initialization') {
      steps {
        sh 'echo "Initialization"'
        def branch = GetBranch()
        echo "Branch: $branch"
        UploadFile('file1.txt')
      }
    }
  }
}

