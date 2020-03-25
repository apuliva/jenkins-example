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
        
        stage ('Properties') {

            steps {
                def env=readProp['environment']
                echo "environment = ${env}"
                
            }
        }


        
    }
}
