def getGitBranchName() {
    return scm.branches[0].name
}

pipeline {
  agent any

  stages {
    stage('Initialize') {
      steps {
        getGitBranchName()
        // branch is in GIT_BRANCH environment variable (eg origin/dev)
      }
    }
  }
}