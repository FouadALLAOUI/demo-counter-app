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

        stage('UNIT Testing'){
            
            steps{
                sh 'mvn test'
            }
        }

        stage('Integration Testing'){
            steps{
                sh 'mvn verify -DskipUnitTests'
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