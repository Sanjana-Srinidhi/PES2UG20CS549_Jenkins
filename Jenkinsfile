pipeline {
agent any
tools { 
      maven 'MAVEN_HOME' 
      jdk 'JAVA_HOME' 
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
