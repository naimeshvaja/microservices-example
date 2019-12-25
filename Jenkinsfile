node {
  try {
    stage('Checkout') {
      checkout scm
    }
    stage('Test') {
      sh 'docker-compose run –rm test'
    }
    stage('Build') {
      sh 'docker-compose up --build'
    }
    stage('Clean Docker test'){
      sh 'docker rmi 4111997/microservice'
    }
    stage('Deploy'){
      if(env.BRANCH_NAME == 'master'){
        sh 'docker-compose up --build'
      }
    }
  }
  catch (err) {
    throw err
  }
}