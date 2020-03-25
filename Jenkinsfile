pipeline {
    
    
    agent any
    
    environment {
        
        def readProp=readProperties file: 'environment_dev.properties'
        
    }
    
    tools {
        maven 'Maven_v' 
    }

    stages {
        stage ('Compile Stage') {

            steps {
                
                def readProp1=readProperties file: 'environment_dev.properties'
                echo "${readProp1['environment']}"
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
