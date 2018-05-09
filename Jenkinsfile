pipeline {
  agent none
  stages {
    stage('Creating QE and RC build') {
      parallel {
        stage('Creating QE and RC build') {
          steps {
            sh 'echo "Create QE and RC Build"'
          }
        }
        stage('Upload cookbook and git refs ') {
          steps {
            sh 'echo "apply template"'
          }
        }
        stage('Apply Template') {
          steps {
            sh 'echo "Applying template"'
          }
        }
      }
    }
    stage('ES Deploy') {
      steps {
        sh 'echo "Upgrading deployment"'
      }
    }
    stage('Regression Testing') {
      parallel {
        stage('Regression Testing') {
          steps {
            sh 'echo "executing regression testsuite"'
          }
        }
        stage('Test1') {
          steps {
            sh 'echo "test1"'
          }
        }
        stage('Test2') {
          steps {
            sh 'echo "test1"'
          }
        }
        stage('Test3') {
          steps {
            sh 'echo "test1"'
          }
        }
        stage('Test4') {
          steps {
            sh 'echo "test1"'
          }
        }
        stage('Test5') {
          steps {
            sh 'echo "test1"'
          }
        }
      }
    }
    stage('Genrate Tag') {
      steps {
        sh 'echo "Genrating tag"'
      }
    }
  }
}