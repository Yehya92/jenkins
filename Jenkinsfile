pipeline {
    agent {label 'worker'}

    stages {

 

        stage('Build Backend') {
            steps {
                dir('backend') {
                    sh 'mvn clean package -DskipTests'
                }
            }
        }

        stage('Test Backend') {
            steps {
                dir('backend') {
                    sh 'mvn clean package -DskipTests'
                }
            }
        }

        stage('Archive') {
            steps {
                archiveArtifacts artifacts: 'backend/target/*.jar', fingerprint: true
            }
        }
		stage('Build Frontend') {
    steps {
        dir('frontend') {
            sh 'npm install'
            sh 'npm run build'
        }
    }
}
    }
}