pipeline{
    agent{
        node{
            label 'JenkinsSlaveNodeLabel'
        }
    }
    stages{
        stage('Checkout Code Stage'){
            steps{
                git url:'https://github.com/Priti407/cicdprojectrepo.git' branch:'main'
                }
            }
        stage('Build Docker Image') {
            steps{
                sh 'docker build -t myimage .'
            }
        }
        stage('Push Image To DockerHub'){
            steps{
                sh 'docker tag myimage Priti407/myimage'
                sh 'docker push Priti407/myimage'
            }
        }
        stage('Deploy to Kubernetes'){
            steps{
                sh 'kubectl apply -f my-deployment.yml'
            }
        }  
    }
}