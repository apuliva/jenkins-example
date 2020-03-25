pipeline {
    
    
    agent any
    
    
    
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
                script{
                    def readProp=readFile "environment_dev_prop.yaml"
                    def environment = readYaml text: readProp
                    println "environment =" + environment

                }
            }
        }


        
    }
}
