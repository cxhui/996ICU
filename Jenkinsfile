pipeline {
  agent any
  stages {
    stage('test1') {
      parallel {
        stage('test1') {
          steps {
            archiveArtifacts(artifacts: 'a-name-1', allowEmptyArchive: true)
            bat(script: 'echo', encoding: 'echo1')
          }
        }

        stage('Edge Test') {
          steps {
            pwd(tmp: true)
          }
        }

      }
    }

    stage('Build1') {
      parallel {
        stage('Build1') {
          steps {
            bat 's1'
            build 'Job1'
          }
        }

        stage('Build2') {
          steps {
            emailext(subject: 'subject1', body: '1')
          }
        }

      }
    }

  }
}