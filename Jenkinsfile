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

    stage('Execute Test') {
      parallel {
        stage('Execute Test') {
          steps {
            echo 'Executing Tests'
          }
        }

        stage('Confirm Test') {
          steps {
            input(message: 'Do you want to continue', id: 'Ok')
          }
        }

      }
    }

  }
  environment {
    ChromeDriverPath = '~/Automation/webdrivers'
  }
}