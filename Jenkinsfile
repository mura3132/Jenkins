pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        bat 'F:\\Khbich\\2CS\\new\\OUTILS\\tp\\gradle-6.0.1\\bin\\gradle build'
        bat 'F:\\Khbich\\2CS\\new\\OUTILS\\tp\\gradle-6.0.1\\bin\\gradle javadoc'
        archiveArtifacts 'build/docs/javadoc/**, build/libs/**'
        junit 'build/test-results/test/*.xml'
      }
    }

    stage('Mail Notification') {
      steps {
        emailext(subject: 'Build', attachLog: true, body: 'This is the result of the build', to: 'chekla31@gmail.com')
      }
    }

  }
}