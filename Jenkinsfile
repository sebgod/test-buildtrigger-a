pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        echo 'This is build A'
        sh 'uname -a'
        
        def manualTrigger = true
        currentBuild.upstreamBuilds?.each { b ->
          echo "[INFO] Upstream build: ${b}"
          manualTrigger = false
        }
        if (manualTrigger)
        {
            echo "[INFO] This build was triggered manually"
        }
      }
    }
  }
}
