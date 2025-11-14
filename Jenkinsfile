pipeline {
  agent any

  stages {
    stage('Checkout') {
      steps {
        checkout scm
      }
    }

    stage('Build') {
      steps {
        echo 'Building...'
        // add your build steps here, e.g. sh 'mvn -B -DskipTests clean package' or sh 'npm ci && npm run build'
      }
    }

    stage('Test') {
      steps {
        echo 'Running tests...'
        // add test steps here, e.g. sh 'mvn test' or sh 'npm test'
      }
    }

    stage('Deploy') {
      when {
        branch 'main'
      }
      steps {
        echo 'Deploying...'
        // add deploy steps here
      }
    }
  }

  post {
    always {
      echo 'Pipeline finished'
    }
    success {
      echo 'Success!'
    }
    failure {
      echo 'Failure!'
    }
  }
}