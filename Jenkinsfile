node {
  stage('Clean workspace') {def mvnHome = tool 'M3'
   	deleteDir()
  }
   stage('Preparation') { // for display purposes
      mvnHome = tool 'M3'
   }
   stage('Build') {
         sh "'${mvnHome}/bin/mvn' -Dmaven.test.failure.ignore clean package"
      }
}
