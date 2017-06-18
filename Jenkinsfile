def project_scm = [ url: "https://github.com/Arkariang/pipeline.git", branch: "master"]

pipeline {
  agent any

  stages {
    stage("Build") {
      steps {
        echo "Building"
        git(url: project_scm.url, branch: project_scm.branch)                    
        sh('''
        npm install
        npm run build
        ''')
      }
    }
    stage("Code check") {
      steps {
        parallel(
            "test": {
              echo "Testing"
              git(url: project_scm.url, branch: project_scm.branch)                    
              sh('''
              npm run test
              ''')
            }
          )
      }
    }
  }
}