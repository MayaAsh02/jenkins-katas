pipeline {
  agent any
  stages {
    stage('Parallel execution') {
      parallel {
        stage('say hello world') {
          steps {
            sh 'echo "hello world"'
          }
        }

        stage('build-app') {
          agent {
            docker {
              image 'gradle:jdk17-alpine'
            }

          }
          steps {
            sh 'ci/build-app.sh'
          }
        }

      }
    }

  }
}