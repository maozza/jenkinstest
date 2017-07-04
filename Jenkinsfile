node {
def config = [:]
    body.resolveStrategy = Closure.DELEGATE_FIRST
    body.delegate = config
    body()
	env.IS_RELEASE_BUILD = '0'
    echo 'input parameters:'
    for ( e in config ) {
        print "${e.key} = ${e.value}"
    }

	properties(
		[
			parameters([
				string(name: 'MAVEN_ADDITIONAL_PARAM', defaultValue: '', description: 'additional parameters to maven command line, i.e. "-X" to add debug information to the log')
			]),
			pipelineTriggers([
				triggers: [
					 [
						  $class: 'hudson.triggers.SCMTrigger',
						  scmpoll_spec : 'H/3 * * * *'
					 ]
				]
			]),
			[$class: 'BuildDiscarderProperty',
				strategy:
					[$class: 'LogRotator',
						artifactDaysToKeepStr: '',
						artifactNumToKeepStr: '',
						daysToKeepStr: '',
						numToKeepStr: '10']
			],
			disableConcurrentBuilds()
		])











   stage('Preparation') { // for display purposes
      mvnHome = tool 'M3'
      sh 'pwd'
      sh 'ls -l'
   }
   stage('Build') {
         sh "set;env"
      }
}
