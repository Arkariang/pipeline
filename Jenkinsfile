def taco_scm = [ url: "https://github.int.midasplayer.com/taco/taco-react.git", branch: "feature/build_system"]

pipeline {
  agent any

  stages {
    stage("Build") {
      steps {
        node('docker && linux') {
          echo "Building"
          git(url: taco_scm.url, branch: taco_scm.branch)                    
          sh('''
docker build -t taco-base . 
docker run -i --rm --name taco-build-container taco-base npm run build
          ''')
        }
      }
    }
    stage("Code check") {
      steps {
        parallel(
              "test": {
                node('docker && linux') {
                  echo "Testing"
                  git(url: taco_scm.url, branch: taco_scm.branch)                    
                  sh('''
        docker build -t taco-base . 
        docker run -i --rm --name taco-test-container taco-base npm run test
                  ''')
                }
              }
          )
      }
    }
  }
}