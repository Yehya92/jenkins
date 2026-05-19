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

        stage('Archive Artifacts') {
    steps {
        archiveArtifacts artifacts: '''
backend/target/*.jar
frontend/build/**
''', fingerprint: true
    }
}
stage('Debug') {
    steps {
        sh 'ls -R backend/target || true'
        sh 'ls -R frontend/build || true'
    }
}
		stage('Deploy') {
    steps {
        echo 'Déploiement à venir'
    }
        }
    }
}