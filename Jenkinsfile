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
      parallel {
        stage('Code Analysis') {
          steps {
            withSonarQubeEnv('sonar') {
              bat 'F:\\Khbich\\2CS\\new\\OUTILS\\tp\\gradle-6.0.1\\bin\\gradle sonarqube'
            }

            waitForQualityGate true
          }
        }

        stage('Test reporting') {
          steps {
            bat 'F:\\Khbich\\2CS\\new\\OUTILS\\tp\\gradle-6.0.1\\bin\\gradle jacocoTestCoverageVerification'
          }
        }

      }
    }

    stage('Slack Notification') {
      steps {
        slackSend(message: 'Integration terminée', channel: 'tp6')
      }
    }

  }
}