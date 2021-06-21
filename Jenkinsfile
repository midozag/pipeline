node{
  stage('SCM Checkout'){
     git 'https://github.com/midozag/pipeline'
  }
  stage('Compile-Package'){
     sh 'mvn package'
  }

}
