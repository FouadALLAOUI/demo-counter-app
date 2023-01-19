pipeline{
    
    agent any 
    tools { 
        maven 'Maven3' 
        //jdk 'jdk8' 
    }
    
    stages {
        
        stage('Git Checkout'){
            
            steps{
                
                script{
                                       
                    git 'https://github.com/FouadALLAOUI/demo-counter-app.git'
                }
            }
        }
           
        stage('UNIT testing'){
            
            steps{
                
                script{                  
                    sh 'mvn test'
                }
            }
        }
        
        stage('Integration testing'){
            
            steps{
                
                script{
                    
                    sh 'mvn verify -DskipUnitTests'
                }
            }
        }
        
        stage('Maven build'){
            
            steps{
                
                script{
                    
                    sh 'mvn clean install'
                }
            }
        }

        stage('Static code analysis'){
            steps{
                withSonarQubeEnv(credentialsId: 'sonar-api-key') {
                    sh 'mvn clean package sonar:sonar'
                }
            }
        }




        /*
        stage('Maven build'){
            
            steps{
                
                script{
                    
                    sh 'mvn clean package'
                }
            }
        }
        */
    }
        
}