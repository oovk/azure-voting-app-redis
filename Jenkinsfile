pipeline {
   agent any
   
   stages {
      stage("Veryfy Branch") {
         steps {
            echo "$GIT_BRANCH"
         }
      }
   stage('Docker Build') {
      steps{
         pwsh(script: 'docker images -a')
         pwsh(script: """
            cd azure-vote/
            docker images -a
            docker build -t Dockerfile-for-app-service .
            docker images -a
            cd ..
         """)
         }  
      }
   }
}