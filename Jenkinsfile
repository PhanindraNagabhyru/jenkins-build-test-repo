node('master')
{
	stage ('checkout') {

	checkout changelog: false, poll: false, scm: [$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/PhanindraNagabhyru/jenkins-build-test-repo.git']]]
	}

	stage('maven fail test')
	{

	sh 'mvn -Dtest=FailingApplicationTests test'
        /*def out = sh script: 'date +%F-%T', returnStdout: true
	def folder = out.trim()+'.'+'zip'
        println "${folder}"
		sh "zip -r ${folder} ./*"*/
	println ('failed')

	}
}
