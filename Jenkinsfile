node('php'){
    stage('Clean'){
        deleteDir()
        sh 'ls -la'
    }

    stage('Fetch') {
        checkout scm
    }

    stage('Docker Build') {
        sh 'sudo docker build -t samuelbartag/laravel:$BUILD_NUMBER .'
    }

    stage('Docker Ship') {
        sh 'sudo docker push samuelbartag/laravel:$BUILD_NUMBER'
    }
    
    stage('Docker Clean') {
        sh 'sudo docker rmi -f samuelbartag/laravel:$BUILD_NUMBER'
    }
}
