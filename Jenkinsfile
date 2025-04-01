pipeline {
    agent { lable 'Jenkins_Agnet' }
    tools {
        jdk 'Java17'
        maven 'Maven3'
    }
  stages {
            stage("Cleanup Workspace") {
                  steps {
                    cleanWs()
                  }
            }
    
            stage("Checkout from SCM") {
                  steps {
                    git branch: 'main', CredentialsId: 'github', url: 'https://github.com/Surendardev08/simple-reactjs-app'
                  }
            }
    
            stage("Build Application") {
                  steps {
                    sh "mvn clean package"
                  }
            }
    
            stage("Test Application"){
                    steps {
                      sh "mvn test"
                    }
            }
        }      
}
