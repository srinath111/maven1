node('built-in') {
    stage('continuous intgration_sri'){
    git 'https://github.com/srinath111/maven1.git'
    }
    stage('continuous build_sri'){
        sh 'mvn package'
    }
    stage('continuous devlivery_sri'){
        deploy adapters: [tomcat9(credentialsId: 'dac6c3c8-4e2a-4a72-a378-0cdf72041db0', path: '', url: 'http://10.1.4.81:8080')], contextPath: 'sri12', war: '**/*.war'
    }
}

