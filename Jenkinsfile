 @Library('piper-lib-os') _
 node() {
    stage('prepare') {
        checkout scm
        setupCommonPipelineEnvironment script:this
    }
    stage('build') {
      mtaBuild script: this
    }
    stage('deploy') {
        def mtarFilePath = commonPipelineEnvironment.getMtarFilePath()
        cloudFoundryDeploy( script: this, mtaPath: mtarFilePath)
    }
}
