pipeline {
    agent any
    
    datas = readYaml file: 'environment_dev_prop.yaml'
    
    tools {
        maven 'Maven_v' 
    }

    stages {
        stage ('Compile Stage') {

            steps {
                withMaven(maven : 'Maven_v') {
                    sh 'mvn clean compile'
                    sh 'echo $environment'
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
