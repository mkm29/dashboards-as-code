def getGitBranchName() {
    return scm.branches[1].name
}

pipeline {
  agent any

  stages {
    stage('Initialize') {
      steps {
        // print out the current git branch
        echo "Current git branch: ${GIT_BRANCH}"
        // branch is in GIT_BRANCH environment variable (eg origin/dev)
      }
    }
  }
}