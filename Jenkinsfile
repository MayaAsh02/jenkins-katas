pipeline {
  agent {
    node {
      label 'gradle:6-jdk11'
    }

  }
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
            node {
              label 'gradle:6-jdk11'
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