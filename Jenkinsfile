pipeline {
    agent any
	tools {
        maven 'Maven'
        jdk 'Java 9'
    }
    stages {
        stage('Build') {
			steps {
				git url: 'https://github.com/zpYura/spring-petclinic.git'
				bat 'mvn clean package'
				archiveArtifacts artifacts: '**/target/*.jar', fingerprint: true 
			}
			post {
                success {
                    junit 'target/surefire-reports/**/*.xml' 
                }
            }
		}
		stage('SonarQube analysis') {
			steps {
				withSonarQubeEnv('sonar') {
					bat 'mvn org.sonarsource.scanner.maven:sonar-maven-plugin:3.2:sonar'
				}
			}
		}
    }
}