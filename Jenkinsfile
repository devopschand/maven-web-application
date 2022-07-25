node{
    def mavenHome=tool name: "maven3.8.6"
    
    stage('CheckoutCode'){
       git branch: 'development', credentialsId: '4cfeb083-9b59-46d1-a088-3250581dfc84', url: 'https://github.com/devopschand/maven-web-application.git' 
         }
    stage('Build'){
        sh "${mavenHome}/bin/mvn clean package"
    }
    stage('ExecureSonarQube Report'){
        sh "${mavenHome}/bin/mvn sonar:sonar"
    }
    stage('Generating Nexus Report'){
        sh "${mavenHome}/bin/mvn deploy"
    }

}
