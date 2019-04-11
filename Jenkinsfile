properties([[
  $class  : 'BuildDiscarderProperty',
  strategy: [$class: 'LogRotator', numToKeepStr: '5']
]])
      
if (env.JOB_NAME.startsWith('mono-mb')) {
    runCIOnMonoRepo()
} else {
    runPipelineOnIndividualProject()
}

def runCIOnMonoRepo() {
  println("runCIOnMonoRepo")
  node {
    stage('checkout') {
      def scmVars = checkout scm
      println(scmVars)
      def commitHash = scmVars.GIT_COMMIT
      println(commitHash)
      sh "printenv"
      git branch: env.BRANCH_NAME, url: 'https://github.com/ian-zy/monomono.git'
      def files = currentBuild.changeSets
                .collectMany { it.items }
                .collectMany { it.affectedFiles }
                .collect { it.path }
            
      println("Files Changed:")
      println(files)
      sh "printenv"
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
