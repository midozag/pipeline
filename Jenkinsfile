node{
  stage('SCM Checkout'){
     git 'https://github.com/midozag/pipeline'
  }
  stage('Compile-Package'){
     def mvnHome = tool name: 'maven-3', type: 'maven'
     sh "${mvnHome}/bin/mvn package"
  }
  stage('Deploy'){
    sshagent(['ec2-user-tomcat']) {
       sh 'scp -o StrictHostKeyChecking=no target/*.war ec2-user@3.12.153.1:/opt/apache-tomcat-8.5.43/webapps'

     }
  }

}
