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
			}
		}
		/*stage('SonarQube analysis') {
			steps {
				withSonarQubeEnv('sonar') {
					bat 'mvn org.sonarsource.scanner.maven:sonar-maven-plugin:3.2:sonar'
				}
			}
		}*/
    }
}