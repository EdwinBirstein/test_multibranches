pipeline {
  agent {
    label 'Linux'
        }
    stages {
      stage ('Compilation') {
             sh 'mvn package'
             }
     stage ('Execution') {
             sh 'mvn test'
          }
    stage ('Script') {
    steps {
        sh 'chmod +x test_mb_jenkins.sh'
        sh './test_mb_jenkins.sh'
      }
    }
     stage ('Déploiement') {
             sh 'curl -u admin:Box.Or@nge1 --upload-file test_maven-1.0-SNAPSHOT.jar 'http://10.10.20.31:8081/repository/depot_test/test.jar''
          }   
}
}
