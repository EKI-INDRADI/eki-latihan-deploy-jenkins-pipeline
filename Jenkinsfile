
def configDate ="27/06/2022"


pipeline {
  agent any
  stages {


        stage("Build WHOAMI") {
          steps {
            echo "whoami . . . Date : ${configDate}"
            sh """
            whoami
            """
          }
      }
    
    stage("Build PWD") {
          steps {
            echo "pwd . . . Date : ${configDate}"
            sh """
            pwd
            """
          }
    }





  }


}
