def getGitBranchName() {
    return scm.branches[0].name
}

pipeline {
  agent any

  stages {
    stage('Initialize') {
      steps {
        // print out the current git branch
        echo "Current git branch: ${getGitBranchName()}"
        // branch is in GIT_BRANCH environment variable (eg origin/dev)
      }
    }
  }
}