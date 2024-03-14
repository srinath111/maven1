node('built-in') {
    stage('continuous intgration_sri'){
    git 'https://github.com/srinath111/maven1.git'
    }
    stage('continuous build_sri'){
        sh 'mvn package'
    }
    stage('continuous devlivery_sri'){
        deploy adapters: [tomcat9(credentialsId: 'db8b7ed0-501d-4d83-b874-6b42ce600110', path: '', url: 'http://10.1.4.81:8080')], contextPath: 'test2app', war: '**/*.war'
    }
    stage('continuous testing'){
        git 'https://github.com/srikorboina/sr.git'
        sh 'java -jar /root/.jenkins/workspace/script/testing.jar'
    }
}

