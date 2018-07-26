pipeline {
	agent any
	stages {
		stage('Build') {
			environment {
				ANYPOINT_CREDENTIALS = credentials("${ENV}.cloudhub.credentials")
				TWITTER_ACCESS_KEY = credentials("${ENV}.twitter.access.key")
				TWITTER_ACCESS_SECRET = credentials("${ENV}.twitter.access.secret")
				TWITTER_CONSUMER_KEY = credentials("${ENV}.twitter.consumer.key")
				TWITTER_CONSUMER_SECRET = credentials("${ENV}.twitter.consumer.secret")
			}
			steps {
				sh 'mvn clean package deploy -DmuleDeploy -Dusername=${ANYPOINT_CREDENTIALS_USR} -Dpassword=${ANYPOINT_CREDENTIALS_PSW} -Dhttp.port=8081 -Dtwitter.access.key=${TWITTER_ACCESS_KEY} -Dtwitter.access.secret=${TWITTER_ACCESS_SECRET} -Dtwitter.consumer.key=${TWITTER_CONSUMER_KEY} -Dtwitter.consumer.secret=${TWITTER_CONSUMER_SECRET}'
			}
		}
	}
}