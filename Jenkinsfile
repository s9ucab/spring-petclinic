pipeline {
        agent { label 'build' }

   stages {
      stage ('Maven Build') {
         steps {
            echo 'Maven Build'
            sh './mvnw package -DskipTests'
	 }
      }
      stage ('Docker Build') {
         steps {
            echo 'Docker Build'
            sh 'docker build . -t s9ucab/spring-clinic'
            sh 'docker tag s9ucab/spring-clinic:latest s9ucab/spring-clinic:${VERSION}'
         }
      }
      stage ('Docker Push') {
         steps {
                 sh 'docker push s9ucab/spring-clinic:${VERSION}'
         }
      }
   }
}     
