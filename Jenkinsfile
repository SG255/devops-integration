pipeline{
    agent any
    tools{
        maven 'maven'
       
    }
        
    
    stages{
        stage('build maven'){
            steps{
                checkout scmGit(branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/SG255/devops-integration']])
                sh 'mvn clean install'
            }
        }
         stage('Build docker image'){
            steps{
                script{
                    sh 'docker build -t kumarsg137/devops-integration .'
                }
            }
        }
        stage('Push image to Hub'){
            steps{
                script{
                
                   sh 'docker login -u kumarsg137@gmail.com -p Aaradhya630$'


                   sh 'docker push kumarsg137/devops-integration'
                }
            }
        }
        
    }
    
}