#!groovy

node {

	properties([
		pipelineTriggers([
			[
				$class: 'hudson.triggers.TimerTrigger',
				spec  : "H 0 * * 0"
			]
		]),
		disableConcurrentBuilds()
	])

	stage("2nd Job") {
	
		echo "******** 2nd Job test Start ********"

		sh "echo ${env.JOB_NAME} > 2nd_job.txt"
		sh "echo ${env.BRANCH_NAME} >> 2nd_job.txt"

		archive "2nd_job.txt"
		sleep(60)
		echo "******** 2nd Job test End ********"

	}
}
