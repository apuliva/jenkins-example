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
                    //def readProp=readFile "environment_dev_prop.yaml"
                    def read_string = readYaml file : "environment_dev_prop.yaml"
                    //println "environment =" + environment
                    env.envvalue = read_string['environment']
                    println " ${envvalue} "
                    env.ipvalue = read_string['ip_address']
                    println " ${ipvalue} "
                    env.portvalue = read_string['port']
                    println " ${portvalue} "
                    

                }
            }
        }


        
    }
}
