pipeline {
    agent any

    tools {
        maven 'M3'
        jdk 'JDK17'
    }

    stages {
        stage('Git Clone') {
            steps {
                git url: 'https://github.com/whwhdgus126-droid/spring-petclinic.git',
                    branch: 'main'
            }
        }

        stage('Maven Build') {
            steps {
                sh 'mvn -Dmaven.test.failure.ignore=true clean package'
            }
            post {
                success {
                    echo 'Maven Build Success'
                }
                failure {
                    echo 'Maven Build Failed'
                }
            }
        }
pipeline{
  stages{
    stage('Docker Image Build') {
      steps {
        echo 'Docker image Build'
        dir("${env.WORKSPACE}") {
          sh """
          docker build -t spring-petclinic:$BUILD_NUMBER .
          docker tag spring-petclinic:$BUILD_NUMBER whwhdgus126-droid/spring-petclinic:latest
          """
        }
      }
    }
        
    stage('Docker Image Upload') {
            steps {
                echo 'Docker Image Upload'
            }
        }

           
            }
}
        
