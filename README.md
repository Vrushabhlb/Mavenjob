# WebAppForJenkins

Note - 

tools {
        maven "3.6.3"
    }
 
 This will give error like below
Tool type "maven" does not have an install of "3.6.3" configured - did you mean "maven 3.6.3"?


    
    
    - maven 3.6.3 is name i given during maven configuration in global tool configuration, you need to give same name as that in your jenkins file too.
      you should give nlike below
    
          pipeline {
    agent any
    tools {
        maven "maven 3.6.3"
    }
    stages {
        stage('Clean and Install') {
            steps {
               bat 'mvn clean install'
            }
        }
        stage('Package') {
            steps {
               bat 'mvn package'
            }
        } 
    }
}
