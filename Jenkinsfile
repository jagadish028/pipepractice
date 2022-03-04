pipeline {
  agent any
    stages {
		stage('Build') {
			steps {
				sh '''
				cd
				mkdir war
				cd war
				git clone https://github.com/efsavage/hello-world-war.git
				cd hello-world-war
				mvn clean install
				'''
			}
		}
		stage('Deploy') {
			steps {
				sh '''
				cd
				cd /war/hello-world-war/target/
					sudo cp -r *.war /home/ec2-user/tomcat/webapps
					'''
				}	
		}
	}
}
