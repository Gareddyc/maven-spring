env.mvnHome = '/usr/share/maven'
node('maven-label1') {
   
   
   stage('Preparation') { // for display purposes
      
      git 'https://github.com/jglick/simple-maven-project-with-tests.git'
        
      
   }
   stage('Build1') {
      
      if (isUnix()) {
         sh "'${mvnHome}/bin/mvn' clean install"
      } else {
         bat(/"${mvnHome}\bin\mvn" -Dmaven.test.failure.ignore clean package/)
      }
   }
   stage('Results1') {
      junit '**/target/surefire-reports/TEST-*.xml'
      archive 'target/*.jar'
   }
   

}
