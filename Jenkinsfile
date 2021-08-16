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
      stage ('Dockerhub Push') {
         docker.withRegistry('https://registry.hub.docker.com', 'git') {
            app.push("${env.BUILD_NUMBER}")
            app.push("latest")
         }
      }
   }
}     
