pipeline {
    agent any
    
        stages {
            stage("Build") {
                steps {
                    dir("/Users/nicolas/code/estudios/usach/unidad3/ejemplo-maven-main"){
                    sh "./mvnw clean compile -e"
                        
                    }
                    
                }
            }
            stage("Test") {
                steps {
                    dir("/Users/nicolas/code/estudios/usach/unidad3/ejemplo-maven-main"){
                    sh "./mvnw clean test -e"
                        
                    }
                }
            }
            stage("Jar") {
                steps {
                    dir("/Users/nicolas/code/estudios/usach/unidad3/ejemplo-maven-main"){
                    sh "./mvnw clean package -e"
                        
                    }
                }
            }
            stage("Run Jar") {
                steps {
                    dir("/Users/nicolas/code/estudios/usach/unidad3/ejemplo-maven-main"){
                    sh "nohup bash mvnw spring-boot:run &"
                    sh "sleep 10"
                    }
                }
            }
             stage("Test app") {
                steps {
                    dir("/Users/nicolas/code/estudios/usach/unidad3/ejemplo-maven-main"){
                    sh "curl -X GET localhost:8081/rest/mscovid/test?msg=testing"
                    }
                }
            }
           
           
            
        }
    }


