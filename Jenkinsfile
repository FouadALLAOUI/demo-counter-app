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
        stage ('Build') {
                 git url: 'https://github.com/cyrille-leclerc/multi-module-maven-project'
                withMaven {
                        sh "mvn clean package"
                          } // withMaven will discover the generated Maven artifacts, JUnit Surefire & FailSafe reports and FindBugs reports
                        }
        /*stage('Maven build'){
            
            steps{
                
                script{
                    
                    sh 'mvn clean package'
                }
            }
        }
        /*
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
        */
    }
        
}