pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        sh 'mvn -debug clean install -DskipTests=true -Dmaven.wagon.http.ssl.insecure=true -Dmaven.wagon.http.ssl.allowall=true'
        jacoco(sourcePattern: 'src/main/java', classPattern: 'target/classes')
      }
    }

    stage('deploy') {
      steps {
        sh 'java -jar ./target/demo-0.0.1-SNAPSHOT.jar'
      }
    }

    stage('end') {
      steps {
        echo 'build & deploy success'
      }
    }

  }
}