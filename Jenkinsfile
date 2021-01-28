pipeline {
    agent any

    tools {
        // Install the Maven version configured as "M3" and add it to the path.
        maven "maven-gopi"
    }

    stages {
        stage('checkin') {
            steps {
                // Get some code from a GitHub repository
                git branch: 'jenkins_maven', url: 'https://github.com/gopi-1/jenkins_maven.git'
		}
	}
	stage('build') {
            steps {                 
                // Run Maven on a Unix agent.
                sh "mvn -Dmaven.test.failure.ignore=true clean package"

                // To run Maven on a Windows agent, use
                // bat "mvn -Dmaven.test.failure.ignore=true clean package"
            }

           
        }
    }
}
