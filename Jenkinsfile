node {
   stage('Preparation') { // for display purposes
      mvnHome = tool 'M3'
      sh 'pwd'
      sh 'ls -l'
   }
   stage('Build') {
         sh "'${mvnHome}/bin/mvn' -Dmaven.test.failure.ignore clean package"
      }
}
