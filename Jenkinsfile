pipeline {
    agent any 
    tools {
      maven 'maven_home'
    }
    stages {
      stage('maven test ') {
        steps{
            checkout([$class: 'GitSCM', branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/rritsoft/hp-war-test-.git']]])
            bat 'mvn clean package'
             bat 'docker build -t  anjireddy3993/all:2.0   C:/Users/hi/Desktop/dockertest1'
             bat  'docker login -u anjireddy3993  -p ASDasd123$'
             bat 'docker push  anjireddy3993/all:2.0'

            //  withCredentials([string(credentialsId: 'DOCKER-ASDasd123$', variable: 'text')]) {
            //     bat 'docker login -u anjireddy3993  -p ${text}'
            //   }  
          }

        }
    }   

}

