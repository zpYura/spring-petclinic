stage('Build') {
    node {
        git url: 'https://github.com/zpYura/spring-petclinic.git'
        env.PATH = "${tool 'Maven'}/bin:${env.PATH}"
        bat 'mvn clean package'
    }
}

/*stage('SonarQube analysis') {
    node {
        withSonarQubeEnv('sonar') {
            env.PATH = "${tool 'Maven'}/bin:${env.PATH}"
            bat 'mvn org.sonarsource.scanner.maven:sonar-maven-plugin:3.2:sonar'
        }
    }
}*/
