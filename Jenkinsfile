pipeline {

  agent { label 'kubee' }

  stages {

    stage('Checkout Source') {
      steps {
        git url:'https://github.com/shajimonachan/playjenkins.git', branch:'test-deploy-stage'
      }
    }

    stage('Deploy App') {
      steps {
        script {
          kubernetesDeploy(configs: "nginx.yaml", kubeconfigId: "mykubeinfo")
        }
      }
    }

  }

}
