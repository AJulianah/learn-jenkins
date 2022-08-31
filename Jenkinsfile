
pipeline {
  agent { 
    docker{
      image 'mcr.microsoft.com/playwright:v1.25.0-focal'
      args '-u root'
    }
  }
  stages {
    stage('install playwright') {
      steps {
        echo 'This is running'
        sh "npm i -D @playwright/test"
        
        sh "npx playwright install"
        
      }
    }
    stage('help') {
      steps {
        sh "npx playwright test --help"      }
    }
    stage('test') {
      steps {
        sh '''
          npx playwright test --list
          npx playwright test
        '''
      }
    }
  }
}
