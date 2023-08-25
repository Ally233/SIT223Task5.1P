pipeline {
  agent any

  environment {
    DIRECTORY_PATH = "main"
    TESTING_ENVIRONMENT = "main"
    PRODUCTION_ENVIRONMENT = "Ally"
  }

  stages {
    stage('Build') {
      steps {
        echo "Fetching source code from: ${env.DIRECTORY_PATH}"
        echo "Compiling code and generating artifacts"
      }
    }

    stage('Test') {
      steps {
        echo "Running unit tests"
        echo "Running integration tests"
      }
    }

    stage('Code Quality Check') {
      steps {
        echo "Checking code quality"
      }
    }

    stage('Deploy') {
      steps {
        echo "Deploying application to ${env.TESTING_ENVIRONMENT}"
      }
    }

    stage('Approval') {
      steps {
        script {
          echo "Waiting for manual approval..."ss
          sleep(time: 10, unit: 'SECONDS')
        }
      }
    }

    stage('Deploy to Production') {
      steps {
        echo "Deploying code to production environment: ${env.PRODUCTION_ENVIRONMENT}"
      }
    }
  }

  post {
    success {
      echo "Pipeline executed successfully!"
    }
    failure {
      echo "Pipeline failed."
    }
  }
} 
