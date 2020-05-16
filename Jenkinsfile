node('master')
{
	stage ('checkout') {

	checkout changelog: false, poll: false, scm: [$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/PhanindraNagabhyru/jenkins-build-test-repo.git']]]
	}

	stage('maven fail test')
	{
	 //def fail = 'mvn -Dtest=FailingApplicationTests test' 	
         
	 sh 'mvn -Dtest=FailingApplicationTests test -Dmaven.test.failure.ignore=true'
        /*def out = sh script: 'date +%F-%T', returnStdout: true
	def folder = out.trim()+'.'+'zip'
        println "${folder}"
	 	sh "zip -r ${folder} ./*"*/
	 
	catchError(message: 'error')
	 {
           println('failure')
         }
 
	}
	
}
