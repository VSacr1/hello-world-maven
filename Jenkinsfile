pipeline {
    agent any
    
    
    tools {
        // Install Maven version configured as "M3" and add it to the Path
        maven "M3"
    }
    
    stages {
        stage('Checkout'){
            steps {
                //Get some code from GitHub repository
                git branch:'main', url:'https://github.com/VSacr1/hello-world-maven.git'
            }
        }
        stage('Compile'){
            steps {
                //Run maven on a Unix Agent
                sh "mvn clean compile"
            }
        }
        
        stage('Test'){
            steps {
                sh "mvn -Dmaven.compile.skip test"
            }
        }
        
        stage('Package'){
            steps {
                sh "mvn -Dmaven.test.skip -Dmaven.compile.skip package"
            }
        }
    }
}
