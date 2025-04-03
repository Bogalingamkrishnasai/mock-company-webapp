pipeline {
  /*
   * TODO: Implement pipeline stages/steps
   *   See documentation: https://www.jenkins.io/doc/book/pipeline/syntax/#stages
   */
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
                sh './gradlew assemble'
            }
        }

        stage('Test') {
            steps {
                sh './gradlew test'
            }
        }
    }

    post {
        success {
            echo 'Build and Tests Passed! ✅'
        }
        failure {
            echo 'Build or Tests Failed! ❌'
        }
    }
}

}
