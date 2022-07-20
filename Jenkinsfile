pipeline {
  agent any
  stages {
    stage("verify tooling") {
      steps {
        sh '''
          docker version
          docker info
          docker-compose --version 
          curl --version
          
        '''
      }
    }
    stage('Prune Docker data') {
      steps {
        sh 'docker system prune -a --volumes -f'
      }
    }
//     stage('Start container') {
//       steps {
//         sh 'docker-compose up'
//         sh 'docker-compose ps'
//       }
//     }
    stage('sleep') {
      steps {
        sh 'sleep 150'
        echo "run next step"
       
      }
    
    }
    
    stage('Run tests against the container') {
      steps {
        echo "serving on browser"
      }
    }
  }
  post {
    always {
//       sh 'docker-compose down'
//       sh 'docker-compose ps'
      echo "cleaned"
    }
  }
}
