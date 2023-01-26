pipeline {
  agent any
  stages {
    stage('test windows') {
      parallel {
        stage('test') {
          steps {
            sh '''echo "test"


'''
          }
        }

        stage('test linux') {
          steps {
            sh 'echo "test"'
          }
        }

      }
    }

    stage('verif') {
      steps {
        fileExists 'pom.xml'
        sh 'ls -la'
      }
    }

    stage('build') {
      steps {
        sh 'mvn clean install'
      }
    }

    stage('publish report') {
      steps {
        echo 'publish'
      }
    }

    stage('deploy') {
      steps {
        sh 'echo "deploy"'
      }
    }

  }
  environment {
    test = 'test'
  }
}