node('master')
{
	stage ('checkout') {

	checkout changelog: false, poll: false, scm: [$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/PhanindraNagabhyru/jenkins-build-test-repo.git']]]
	}

	stage('maven pass test')
	{

	sh 'mvn -Dtest=WorkingApplicationTests test'
        def folder = sh script: 'date +%F-%T', returnStdout: true	 
	 zip ${folder}.zip $WORKSPACE/
	 println ('success')

	}
}
