pipeline {
  agent any
  stages {
    stage('Parallel execution') {
      parallel {
        stage('say hello world') {
          steps {
            sh 'sh \'\'\'echo "hello world"\'\'\''
          }
        }

        stage('build-app') {
          agent {
            docker {
              image 'gradle:6-jdk11'
            }

          }
          steps {
            sh 'sh \'ci/build-app.sh\''
          }
        }

      }
    }

  }
}