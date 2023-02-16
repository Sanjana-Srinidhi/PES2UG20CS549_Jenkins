pipeline {
agent any
tools { 
      maven 'Maven 3.3.9' 
      jdk 'jdk8' 
    }
stages {
    stage('Build') {
        steps {
            sh 'g++ -o PES2UG20CS549-1 pipeline.cpp'
        }
    }
    
    stage('Test') {
        steps {
            sh './PES2UG20CS549-1'
        }
    }
    
    stage('Deploy') {
        steps {
            // deployment code
            sh 'mvn deploy'
            echo 'Pipeline successful'
        }
    }
}

post {
    always {
        script {
            if (currentBuild.result == "FAILURE") {
                echo "Pipeline failed"
            }
        }
    }
}
}
