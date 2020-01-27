pipeline {
  agent any
  stages {
    stage('error') {
      steps {
        bat 'F:\\Khbich\\2CS\\new\\OUTILS\\tp\\gradle-6.0.1\\bin\\gradle build'
        bat 'F:\\Khbich\\2CS\\new\\OUTILS\\tp\\gradle-6.0.1\\bin\\gradle C:\\Program Files\\Java\\jdk1.8.0_231\\bin\\javadoc'
        archiveArtifacts './build/docs/javadoc/**'
        archiveArtifacts './build/doc/javadoc/**'
        archiveArtifacts './build/test-results/test/**'
      }
    }

  }
}