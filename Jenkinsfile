pipeline {
   agent build

   stages {
      stage ('Maven Build') {
         steps {
            echo 'Maven Build'
            mvnw package -DskipTests
	 }
      }
      stage ('Docker Build') {
         steps {
            echo 'Docker Build'
            docker build . -t spring-clinic
         }
   }
}     
