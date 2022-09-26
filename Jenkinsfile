pipeline{
    agent any
    stages{
        stage('cloning code from spc repository'){
            steps{
             git branch: 'main', url: 'https://github.com/gitforpractise/spring-petclinic.git'
            }
             
        }
        stage('creating package'){
            steps{
                sh 'mvn package'
            }
        }
        stage('archiving artifacts'){
            steps{
                archiveArtifacts artifacts: 'target/*.jar', followSymlinks: false
            }
        }
        stage('unit test results'){
            steps{
                junit 'target/surefire-reports/*.xml'
            }
        }
    }
}
