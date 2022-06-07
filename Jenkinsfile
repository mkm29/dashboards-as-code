def UploadFile(String file_name) {
  echo "Uploading $file_name"
}

def GetBranch() {
  return $GIT_BRANCH.split('/')[1]
}

node {
  agent any
  stage('Initialization') {
    sh 'echo "Initialization"'
    String branch = GetBranch()
    echo "Branch: $branch"
    UploadFile('file1.txt')
  }
}

