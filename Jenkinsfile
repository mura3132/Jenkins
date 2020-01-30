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
        mail(subject: 'Build', body: 'The build has finished', to: 'chekla31@gmail.com')
      }
    }

    stage('Code Analysis') {
      steps {
        waitForQualityGate true
      }
    }

  }
}