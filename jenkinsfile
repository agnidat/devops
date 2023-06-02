Jenkinsfile

pipeline {
  agent any
  stages {
    stage('Checkout Scm') {
      steps {
        git 'https://github.com/agnidat/devops.git'
      }
    }

    stage('Maven Build 0') {
      steps {
        sh 'mvn package'
      }
    }

  }
  tools {
    maven 'Maven'
    jdk ''
  }
  post {
    always {
      step(followSymlinks: false, artifacts: '**/*.war', $class: 'ArtifactArchiver')
    }

  }
}
