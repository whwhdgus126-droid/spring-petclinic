pipeline {
  agent any

  tools {
    maven "M3"
    fdk "JDK17"
  }

  stage {
    stage('Git Clone') {
      steps {
        git url: 'https://github.com/whwhdgus126-droid/spring-petclinic.git/',branch: 'main'
      }
    }
  }
}
