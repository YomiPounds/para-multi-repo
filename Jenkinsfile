pipeline{
    agent any 
    stages{
        stage('clone-fron-jenkins'){
            steps{
                checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: 'jenkinsgit', url: 'https://github.com/YomiPounds/para-multi-repo.git']]])
            }
        }
        stage('parallel-stage'){
            parallel{
                stage('parallel-jobs'){
                    steps{
                        sh 'whoami'
                        sh 'lscpu'
                    }
                }
                stage('parallel-2'){
                    steps{
                        echo "the only way is a lot of practise!!!!!!"
                    }
                }
            }
        }
        stage('second-level-stage'){
            steps{
                echo "this is getting better"
            }
        }
        stage('stage-testcondition'){
            when{
                branch 'uat'
            }
            steps{
                echo "skipping stages"
                sh 'chmod +x yomi.sh'
                sh 'bash -x idris.sh'
            }
        }
    }
}