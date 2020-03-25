pipeline {
    
    
    agent any
    
    environment {
        
        def readProp=readYaml file: 'environment_dev_prop.yaml'
        
    }
    
    tools {
        maven 'Maven_v' 
    }

    stages {
        stage ('Compile Stage') {

            steps {
                
                echo "${readProp['environment']}"
                withMaven(maven : 'Maven_v') {
                    sh 'mvn clean compile'
                    
                }
            }
        }

        stage ('Testing Stage') {

            steps {
                withMaven(maven : 'Maven_v') {
                    sh 'mvn test'
                }
            }
        }


        
    }
}
