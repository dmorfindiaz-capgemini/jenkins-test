pipeline{
    agent{label 'master'}
    tools{maven 'M3'}
    stages{
        stage('Git-Checkout'){
            steps{
                git branch: 'master', url: 'https://github.com/dmorfindiaz-capgemini/jenkins-test.git'
            }
        }
        stage('Build'){
            steps{
                bat 'mvn compile'
            }
        }
        stage('Test'){
            steps{
                bat 'mvn test'
            }
        }
        stage('Package'){
            steps{
                bat 'mvn package'
            }
        }
        stage('Deploy'){
            steps{
                bat 'mvn clean deploy -DmuleDeploy'
            }
        }
    }
}
