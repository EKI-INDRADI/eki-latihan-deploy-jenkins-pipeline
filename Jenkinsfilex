
def configDate ="27/06/2022"


pipeline {
  agent any
  stages {
    
    stage("Build Stage Nodejs Project") {
      parallel { 
        stage("Build deploynodejs1 ") {
          steps {
            echo "Build deploynodejs1 . . . Date : ${configDate}"
            sh """
            node --version
            npm i
            """
          }
        }

        stage("Build deploynodejs2 ") {
          steps {
            echo "Build deploynodejs2 . . . Date : ${configDate}"
            sh """
            node --version
            npm i
            """
          }
        }


      }
    }

    stage("Test Stage") {
      parallel {
        stage("Test API deploynodejs1") {
          steps {
            echo "Testing deploynodejs1. . . Date : ${configDate}"
          }
        }

        stage("Test API deploynodejs2") {
          steps {
            echo "Testing deploynodejs2 . . . Date : ${configDate}"
          }
        }
      }
    }


    stage("Deploy Stage") {
      parallel {
        stage("Deploy API deploynodejs1") {
          steps {
            echo "Deploying deploynodejs1 . . . Date : ${configDate}"
            sh """ 
             pm2 start ./deploynodejs1/deploynodejs1.js --name deploynodejs1
            """
          }
        }

        stage("Deploy API deploynodejs2") {
          steps {
            echo "Deploying deploynodejs2 . . . Date : ${configDate}"
            sh """ 
             pm2 start ./deploynodejs1/deploynodejs2.js --name deploynodejs2
            """
          }
        }
      }
    }


  }


}
