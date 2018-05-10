pipeline {
  agent {
    node {
      label 'ce-devrls-us'
    }
    
  }
  stages {
    stage('Build Validation') {
      steps {
        sh 'echo "creating missing Pull request for targeted Es branch"'
      }
    }
    stage('Create QE Build') {
      parallel {
        stage('Create QE Build') {
          steps {
            sh 'echo "cherry pick all the new ticket changes"'
          }
        }
        stage('Upload Cookbooks') {
          steps {
            sh 'echo "Uploading cookbooks after successful build creation"'
          }
        }
        stage('Create Template') {
          steps {
            sh 'echo "creating ES Release template with updated cookbook version "'
          }
        }
      }
    }
    stage('Deploy') {
      parallel {
        stage('Deploy') {
          steps {
            echo 'Deploy code on deployemnts'
          }
        }
        stage('Upgrade Deployment') {
          steps {
            sh 'echo "upgrade deployemnt with new es release template"'
          }
        }
        stage('Upgrade Release Server') {
          steps {
            sh 'echo "upgrading release server with updated es release template"'
          }
        }
      }
    }
    stage('Tests(Regression)') {
      parallel {
        stage('Tests') {
          steps {
            echo 'Regression testing'
          }
        }
        stage('Bootstrap') {
          steps {
            echo 'Bootstrap instance'
          }
        }
        stage('Upgrade') {
          steps {
            echo 'Upgrade instance'
          }
        }
        stage('Regenrate  All Config') {
          steps {
            echo 'Regenrate all config'
          }
        }
        stage('Instance Validation') {
          steps {
            echo 'stance validation'
          }
        }
        stage('Restart Instacne') {
          steps {
            echo 'Restart Instacne'
          }
        }
        stage('DB Backup') {
          steps {
            echo 'DB Backup'
          }
        }
      }
    }
    stage('Merge PRs') {
      steps {
        echo 'Tag and release'
      }
    }
  }
}