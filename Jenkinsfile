pipeline {
        agent any
        stages{
                stage('Initial setup'){
                        steps{
				sh 'sudo docker-compose down'
                                sh 'echo starting'
                        }
                }
                stage('Checking docker'){
                        steps{
                                sh 'sudo docker ps'
                        }
                }
                stage('Building dockerfile'){
                        steps{
                                sh 'sudo docker build --tag=php54 .'
                        }
                }
                stage('Deploy docker container'){
                        steps{
                                sh 'sudo docker-compose down'
                                sh 'sudo docker-compose -f docker-compose-jen.yml up -d'
                                sh 'ls code -ls;pwd'
                        }
                }
        }
}
