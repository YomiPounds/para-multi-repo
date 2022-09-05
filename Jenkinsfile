pipeline{
    agent any 
    stages{
        stage('clone fron jenkins'){
            steps{
                checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: 'jenkinsgit', url: 'https://github.com/YomiPounds/para-multi-repo.git']]])
            }
        }
    }
}