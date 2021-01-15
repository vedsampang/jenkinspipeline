pipeline {
  agent any
  stages {
    stage('Get Test Scripts for Github') {
      parallel {
        stage('Get Test Scripts for Github') {
          steps {
            echo 'Hi, this is the first step'
          }
        }

        stage('Test') {
          steps {
            sleep 4
            echo """ChromeDriverPath: ${ChromeDriverPath}"""
          }
        }

      }
    }

  }
  environment {
    ChromeDriverPath = '~/Automation/webdriverrs'
  }
}