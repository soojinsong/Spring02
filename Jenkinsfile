pipeline {
    agent any
    
    tools {
        maven 'my-maven'  // 젠킨스에서 설치한 이름
    }

    stages {
        stage('0. 연결 확인999') { steps { echo '스테이지 출발' } }
        
        stage('1. Build') {
            steps {
                echo 'Maven으로 빌드 시작'
                sh 'mvn clean package'
            }
        }        
        stage('2. docker 버전 확인') {
            steps {
                sh 'docker version'
            }
        }
        stage('3. Docker Build(도커 이미지 생성)') {
            steps {
                sh 'docker build -t ex02-app:latest'
            }
        }
    }
}
