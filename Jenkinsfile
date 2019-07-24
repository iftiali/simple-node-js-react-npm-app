pipeline { 
    agent any 
    options {
        skipStagesAfterUnstable()
    }
    stages {
	    stage('Compile') { 
            steps { 
			    withMaven(maven: 'maven_3_6_1'){
					sh 'mvn clean compile' 
				}
			}
        }
        stage('Build') { 
           withMaven(maven: 'maven_3_6_1'){
					sh 'mvn build' 
				}
        }
        stage('Test'){
			withMaven(maven: 'maven_3_6_1'){
					sh 'mvn test' 
				}
        }
        stage('Deploy') {
            steps {
                sh 'echo %hello%'
            }
        }
    }
}
