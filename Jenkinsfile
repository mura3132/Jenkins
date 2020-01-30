pipeline {
  agent any
  stages {
    stage('error') {
      steps {
        bat 'F:\\Khbich\\2CS\\new\\OUTILS\\tp\\gradle-6.0.1\\bin\\gradle build'
        bat 'F:\\Khbich\\2CS\\new\\OUTILS\\tp\\gradle-6.0.1\\bin\\gradle javadoc'
        archiveArtifacts 'build/docs/javadoc/**'
        archiveArtifacts 'build/libs/**'
        junit 'build/test-results/*.xml'
      }
    }

  }
}