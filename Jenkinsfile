node{
    def mvnHome
 
   stage('SetEnv') { 
      git 'https://github.com/Jesmin09/Snykscriptbasedintegration.git'
      mvnHome = tool 'MAVEN_HOME'
	   
   }
   
   stage('CompileandPackage') {
      withEnv(["MVN_HOME=$mvnHome"]) {
            bat(/"%MVN_HOME%\bin\mvn" -Dmaven.test.failure.ignore clean compile/)
         }
      
   }
   stage('Snyk'){
        snykSecurity failOnIssues: false, organisation: '70d5e56b-5700-4632-9f1e-393afcf737aa', snykInstallation: 'snyknew', snykTokenId: 'snykkey'
       
   }

}
