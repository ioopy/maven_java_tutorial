pipeline {
    agent {
        label "master"
    }
    tools {
        maven 'M2_HOME'
        jdk 'JAVA_HOME'
    }
    stages {
        stage ('Initialize') {
            steps {
                bat '''
                    echo "PATH = %PATH%"
                    echo "M2_HOME = %M2_HOME%"
                '''
            }
        }

        stage ('Build') {
            steps {
                    bat 'cd NumberGenerator & mvn install '
                    bat ' pybot E:\\AAAInternship\\Automated_Test\\Robot_test\\Testcase.txt '
            }
             post {
                success {
                    junit 'NumberGenerator/target/surefire-reports/*.xml'
                        }
                 }
            
                 
               

           
            }
       
            
               

           
            
        }
    
}
