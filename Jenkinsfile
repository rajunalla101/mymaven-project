pipeline {
      agent any
    tools { maven 'maven36' }
    options {
            buildDiscarder(logRotator(numToKeepStr: '5'))
            timeout(time: 1, unit: 'HOURS')
            timestamps()
     }
     triggers { upstream(upstreamProjects: 'basic-pipeline-test', threshold: hudson.model.Result.SUCCESS) }
    stages {
        
        stage('build'){
          
            steps{
            
                       sh 'mvn clean package'
                }
        }
    }
}
