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
  // node {
  //   stage('checkout') {
  //     scmVars = checkout([scm: scm, commitId: '2236280f9c7f87980a814679dd7358172b032e3d'])
  //     println(scmVars)
  //     def commitHash = scmVars.GIT_COMMIT
  //     println(commitHash)
  //     sh "printenv"
  //     git branch: env.BRANCH_NAME, url: 'https://github.com/ian-zy/monomono.git'
  //     def files = currentBuild.changeSets
  //               .collectMany { it.items }
  //               .collectMany { it.affectedFiles }
  //               .collect { it.path }
            
  //     println("Files Changed:")
  //     println(files)
  //     sh "printenv"
  //   }
  //   stage('lint') {
  //     sh "pwd && ls"
  //   }
  //   stage('build') {
  //     sh "pwd && ls"
  //   }
  //   stage('unit test') {
  //     sh "pwd && ls"
  //   }
  //   stage('integration test') {
  //     sh "pwd && ls"
  //   }
  // }
  
  // node {
  //     stage('deploy') {
  //         // checkout([scm: scm, commitId:scmVars.GIT_COMMIT])
  //         checkout scm
  //         println(scmVars)
  //     }
  // }
  script('./pipeline.Jenkinsfile')
}

def runPipelineOnIndividualProject() {
  println("runPipelineOnIndividualProject")
}
