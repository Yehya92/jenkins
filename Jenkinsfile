pipeline {
    agent any

    stages {
<<<<<<< HEAD
        stage('Debug Backend Path') {
          steps {
          sh 'ls -R backend'
    }
}
        stage('Deep Backend Inspect') {
    steps {
        sh 'ls -R backend/backend'
    }
}
        stage('Find pom.xml') {
    steps {
        sh 'find . -name pom.xml'
    }
}
        
=======
              
>>>>>>> 0ba9925 (clean backend + Jenkinsfile)

        stage('Build Backend') {
            steps {
                dir('backend/backend') {
                    sh './mvnw clean package -DskipTests=false'
                }
            }
        }

        stage('Test Backend') {
            steps {
                dir('backend/backend') {
                    sh './mvnw test'
                }
            }
        }

        stage('Archive') {
            steps {
                archiveArtifacts artifacts: 'backend/backend/target/*.jar', fingerprint: true
            }
        }
    }
<<<<<<< HEAD
}
=======
}
>>>>>>> 0ba9925 (clean backend + Jenkinsfile)
