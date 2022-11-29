pipeline {
    agent any
    stages {
        stage("verification of the container"){
            steps {
                sh'docker --version'
                //sh '/usr/local/bin/docker-compose ps'
                //script {                
                    //sh'docker ps -q | xargs docker stop'
                    //sh '/usr/local/bin/docker-compose ps'
                //}
            }
        }    
        stage('Docker Build') {
    	    agent any
            steps {
      	        sh 'docker build -t bezkoder-ui:$BUILD_NUMBER .'
                //sh 'docker build -t bezkoder-ui":$BUILD_NUMBER" .'
            }
        }
        stage('start container') {
            steps {
                sh '/usr/local/bin/docker-compose --version'
                sh '/usr/local/bin/docker-compose up'                
                //sh 'docker-compose ps'
            }
        }
        stage('Run tests against the container') {
            steps {
                sh '/usr/local/bin/docker-compose ps'
                //sh 'curl http://localhost:3000/param?query=demo | jq'
            }
        }
    }
    //post {
    //    always {
      //      sh 'docker-compose down'
        //    sh 'docker-compose ps'
        //}
    //}
}
