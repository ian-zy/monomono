properties([[
  $class  : 'BuildDiscarderProperty',
  strategy: [$class: 'LogRotator', numToKeepStr: '5']
]])

println(env.GIT_COMMIT)
      println(env.GIT_BRANCH)
      println(env.GIT_LOCAL_BRANCH)
      println(env.GIT_PREVIOUS_COMMIT)
      println(env.GIT_PREVIOUS_SUCCESSFUL_COMMIT)
      println(env.GIT_URL)
      println(env.GIT_AUTHOR_NAME)
      println(env.GIT_COMMITTER_NAME)
      println(env.GIT_AUTHOR_EMAIL)
      println(env.GIT_COMMITTER_EMAIL)
      
if (env.JOB_NAME.startsWith('mono-mb')) {
    runCIOnMonoRepo()
} else {
    runPipelineOnIndividualProject()
}

def runCIOnMonoRepo() {
  println("runCIOnMonoRepo")
  node {
    stage('checkout') {
      git branch: env.BRANCH_NAME, url: 'https://github.com/ian-zy/monomono.git'
      def files = currentBuild.changeSets
                .collectMany { it.items }
                .collectMany { it.affectedFiles }
                .collect { it.path }
            
      println("Files Changed:")
      println(files)

      println(env.GIT_COMMIT)
      println(env.GIT_BRANCH)
      println(env.GIT_LOCAL_BRANCH)
      println(env.GIT_PREVIOUS_COMMIT)
      println(env.GIT_PREVIOUS_SUCCESSFUL_COMMIT)
      println(env.GIT_URL)
      println(env.GIT_AUTHOR_NAME)
      println(env.GIT_COMMITTER_NAME)
      println(env.GIT_AUTHOR_EMAIL)
      println(env.GIT_COMMITTER_EMAIL)
    }
    stage('lint') {
      sh "pwd && ls"
    }
    stage('build') {
      sh "pwd && ls"
    }
    stage('unit test') {
      sh "pwd && ls"
    }
    stage('integration test') {
      sh "pwd && ls"
    }
  }
}

def runPipelineOnIndividualProject() {
  println("runPipelineOnIndividualProject")
}
