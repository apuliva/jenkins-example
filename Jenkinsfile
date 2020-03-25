pipeline {
    
    def readProp;
    agent any
    
    tools {
        maven 'Maven_v' 
    }

    stages {
        stage ('Compile Stage') {

            steps {
                readProp = readYaml file: 'environment_dev_prop.yaml'
                echo ""${readProp['environment']}""
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
