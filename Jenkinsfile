pipeline {
    agent { label 'worker' }

    stages {

        stage('Build Backend') {
            steps {
                dir('backend') {
                    sh 'mvn clean package'
                }
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

stage('Archive Backend') {
    steps {
        archiveArtifacts artifacts: 'backend/target/*.jar', fingerprint: true
    }
}

sh 'ls -R backend/target'
sh 'ls -R frontend/build'

stage('Archive Frontend') {
    steps {
        archiveArtifacts artifacts: 'frontend/build/**', fingerprint: true
    }
}

		stage('Deploy') {
    steps {
        echo 'Déploiement à venir'
    }
        }
    }
}