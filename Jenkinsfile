pipeline {
  agent any
  stages {
    stage('Test') {
      parallel {
        stage('Maven') {
          steps {
            echo 'Running from Jenkins file'
            //sh(script: 'mvn compile', label: 'maven')
          }
        }

        stage('Cucumber') {
          steps {
            cucumber '**/*.json'
          }
        }
         stage('Email') {
          steps {
            mail bcc: '', body: '''Hi all ,
                  Our Jenkins jobs get passed all the process ''',
                    cc: '', from: 'hariharasudhan9894@gmail.com', 
                    replyTo: '', subject: 'Jenkins Job Passed', 
                    to: 'hariharasudhan0998@gmail.com'

          }
        }
      }
    }

  }
}
