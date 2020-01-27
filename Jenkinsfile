pipeline {
  agent any
  stages {
    stage('') {
      steps {
        bat 'gradle build'
        bat 'gradle javadoc'
        archiveArtifacts './build/docs/javadoc/**'
        archiveArtifacts './build/doc/javadoc/**'
        archiveArtifacts './build/test-results/test/**'
      }
    }

  }
}