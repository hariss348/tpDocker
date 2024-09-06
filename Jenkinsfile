pipeline {
  agent any
  environment {
    IMAGE_NAME = 'mysql'
    IMAGE_NAME1 = 'wordpress'
  }

  stages {
    stage('Utiliser depot'){
      steps {
        checkout scm
      }
    }
    stage('Builder limage'){
      steps{
        script{
          sh 'docker-compose up -d'
        }
      }
    }
    stage('Surveiller etats des services'){
      steps{
        script{
          sh 'docker-compose ps'
        }
      }
    }
    stage('Logs des conteneurs docker'){
      steps{
        script{
          sh 'docker-compose logs'
        }
      }
    }
    stage('Stopper les services'){
      steps{
        script{
          sh 'docker stop $(docker ps -q)'
        }
      }
    }
    
  }
  
}
