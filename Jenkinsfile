pipeline {
  agent any
  stages {
    stage('Parallel execution') {
      parallel {
        stage('say hello world') {
          steps {
            sh '''echo "hello world"
systemctl status docker'''
          }
        }

        stage('build-app') {
          agent {
            docker {
              image 'gradle:6-jdk11'
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