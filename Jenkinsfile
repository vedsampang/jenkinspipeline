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

        stage('Print Message') {
          steps {
            echo """ChromeDriverPath: ${ChromeDriverPath}"""
          }
        }

        stage('Write Test Log') {
          environment {
            LocalVariable = 'HelloLocal'
          }
          steps {
            writeFile(file: 'LogTestFile.txt', text: "This is the value in global environment variable for ChromeDrivePath ${ChromeDriverPath} and localVariable is ${LocalVariable}")
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
      when {
        branch 'main'
      }
      parallel {
        stage('Test') {
          steps {
            echo 'Continuing Tests'
            input(message: 'Continue Tests', id: 'Ok')
          }
        }

        stage('Artifacts') {
          steps {
            archiveArtifacts 'LogTestFile.txt'
          }
        }

      }
    }

  }
  environment {
    ChromeDriverPath = '~/Automation/webdrivers'
  }
}