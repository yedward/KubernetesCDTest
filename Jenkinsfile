pipeline {
   agent any

   stages {
   
      stage('Pull Source Code') {
          steps {
              git credentialsId: 'MyGithub', branch: 'master' , url: 'https://github.com/yedward/KubernetesCDTest.git'
          }
      }
      
      stage('deploy to kubesphere') {
          steps {
            kubernetesDeploy(enableConfigSubstitution: false, kubeconfigId: 'traink8s', configs: 'app.yaml')
          }
      }
   }
}