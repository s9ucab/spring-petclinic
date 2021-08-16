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
            sh 'docker build . -t spring-clinic'
         }
      }
   }
}     
