def getGitBranchName() {
    return scm.branches[1].name
}

pipeline {
  agent any

  stages {
    stage('Initialize') {
      steps {
        // print out the current git branch
        // echo ""
        // branch is in GIT_BRANCH environment variable (eg origin/dev)
        sh '''
            echo "Current git branch: ${GIT_BRANCH.split('/')[1]}"
            echo Changed files
            git diff
        '''
      }
    }
  }
}