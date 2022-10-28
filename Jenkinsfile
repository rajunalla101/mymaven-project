pipeline {
      agent any
    tools { maven 'maven36' }
    options {
            buildDiscarder(logRotator(numToKeepStr: '5'))
            timeout(time: 1, unit: 'HOURS')
            timestamps()devops13-pipeline
     }
     triggers { upstream(upstreamProjects: 'devops13-pipeline/basic-pipeline', threshold: hudson.model.Result.SUCCESS) }
    stages {
        
        stage('build'){
          
            steps{
            
                       sh 'mvn clean package'
                }
        }
    }
}
