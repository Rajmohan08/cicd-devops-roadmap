pipeline {
  agent any

  options {
    disableConcurrentBuilds()
    timestamps()
  }

  environment {
    SITE_URL = 'https://cicd-devops-roadmap.rajmohan.dev/'
  }

  stages {
    stage('Checkout') {
      steps {
        checkout scm
      }
    }

    stage('Validate Site Files') {
      steps {
        script {
          def requiredFiles = ['index.html', 'styles.css', 'app.js', 'CNAME']
          requiredFiles.each { fileName ->
            if (!fileExists(fileName)) {
              error("Missing required site file: ${fileName}")
            }
          }
        }
      }
    }

    stage('Archive Release') {
      steps {
        archiveArtifacts artifacts: 'index.html,styles.css,app.js,CNAME', fingerprint: true
      }
    }

    stage('Approval') {
      when {
        branch 'main'
      }
      steps {
        input message: 'Approve release for GitHub Pages?', ok: 'Deploy'
      }
    }

    stage('Deploy Gate') {
      when {
        branch 'main'
      }
      steps {
        echo 'GitHub Pages remains the hosting platform for this site.'
        echo 'Use Jenkins as the deployment gate before changes are merged or published.'
        echo "After approval, confirm the live site at ${SITE_URL}."
      }
    }
  }
}