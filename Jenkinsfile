node{
stage('clone') {
    git branch: 'main', url: 'https://github.com/gitforpractise/spring-petclinic.git'
   }
stage('creating  package'){
   sh 'mvn package'

}
stage('archiving artifacts')
{
  archiveArtifacts artifacts: 'target/*.jar', followSymlinks: false
}
stage('unit test results')
{
 junit 'target/surefire-reports/*.xml'
}  
}
