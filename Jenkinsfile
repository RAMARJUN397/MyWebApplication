pipeline {
    agent any
    //agent any { docker { image 'maven:3.9.9-eclipse-temurin-21-alpine' } }
     tools{
    maven "M2VEN"
   }
    stages {
        stage('SCM') {
            steps {
                echo 'SCM'
                git branch: 'argroups', url: 'https://github.com/RAMARJUN397/MyWebApplication.git'
            }
        }
        stage('Compile'){
            steps{
                bat 'mvn compile'
                echo 'Code Successfully Compiled By Maven'
            }
        }
         stage('Test'){
            steps{
                bat 'mvn test'
            }
        }
         stage('Build'){
            steps{
                bat 'mvn war:war'
            }
        }
        stage('SMOKE Test'){
            steps{
                echo 'Deploying in Tomcat for Smoke test'
                deploy adapters: [tomcat9(credentialsId: 'TOMCATCRED', path: '', url: 'http://localhost:8081/')], contextPath: 'mydev', war: '**/*.war'
            }
        }
    }
}
