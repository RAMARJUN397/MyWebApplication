pipeline {
  agent any
 tools{
        
        maven  'mvn'
    }
  stages {
    stage ('Setup') {
      steps {
        git branch: 'argroups', url: 'https://github.com/RAMARJUN397/MyWebApplication.git'
      }
    }
    stage ('Compile') {
      steps {
        sh 'mvn compile'
      }
    }
        stage ('Test') {
      steps {
        sh 'mvn test'
      }
    }
    stage ('Build') {
      steps {
        sh 'mvn clean package'
      }
    }
  }
}
