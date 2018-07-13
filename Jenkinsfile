pipeline {
  agent {
    docker {
      image 'maven:3-alpine'
      args '-v /root/.m2:/root/.m2'
    }

  }
  stages {
    stage('Build') {
      parallel {
        stage('Build') {
          steps {
            sh 'mvn -B -DskipTests clean package'
          }
        }
        stage('Shell test 1') {
          steps {
            sh 'hostname -f'
          }
        }
        stage('shell test 2') {
          steps {
            sh 'uptime'
          }
        }
      }
    }
  }
}