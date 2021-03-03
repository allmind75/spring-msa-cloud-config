pipeline {
  agent any
  stages {
    stage('test') {
      steps {
        sh 'mvn -debug clean install -DskipTests=true -Dmaven.wagon.http.ssl.insecure=true -Dmaven.wagon.http.ssl.allowall=true'
      }
    }

  }
}