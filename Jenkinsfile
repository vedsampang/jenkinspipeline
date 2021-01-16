pipeline {
  agent any
  stages {
    stage('Get Test Scripts for Github') {
      parallel {
        stage('Get Test Scripts for Github') {
          steps {
            echo 'Getting code from GitHub'
          }
        }

        stage('Test') {
          steps {
            echo """ChromeDriverPath: ${ChromeDriverPath}"""
          }
        }

        stage('Write Test Log') {
          steps {
            writeFile(file: 'TestLog.txt', text: 'This is the test log', encoding: 'UTF-8')
          }
        }

      }
    }

    stage('Install NPM') {
      steps {
        echo 'Installing NPM'
      }
    }

    stage('Test') {
      steps {
        input(message: 'Continue?', id: 'Yes')
        echo 'Continuing Tests'
      }
    }

  }
  environment {
    ChromeDriverPath = '~/Automation/webdrivers'
  }
}