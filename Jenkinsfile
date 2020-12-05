pipeline {
    agent any
    
        stages {
            stage("Build") {
                steps {
                    
                    sh "./mvnw clean compile -e"
                        
                    
                    
                }
            }
            stage("Test") {
                steps {
                   
                    sh "./mvnw clean test -e"
                        
                    
                }
            }
            stage("Jar") {
                steps {
                    
                    sh "./mvnw clean package -e"
                        
                    
                }
            }

            stage('SonarQube') {
                steps {
                    withSonarQubeEnv(installationName: 'sonar') {
                    sh './mvnw org.sonarsource.scanner.maven:sonar-maven-plugin:3.7.0.1746:sonar'
                }
                }
            }
            stage("Run Jar") {
                steps {
                    
                    sh "nohup bash mvnw spring-boot:run &"
                    sh "sleep 10"
                    
                }
            }
             stage("Test app") {
                
                    sh "curl -X GET localhost:8081/rest/mscovid/test?msg=testing"
                    
                }
            }
           
           
            
        }
    }


