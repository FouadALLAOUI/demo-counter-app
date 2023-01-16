pipeline{
    
    agent any 
    
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
                    echo 'Hello World ==============================********************========================== '                     
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
    }
        
}