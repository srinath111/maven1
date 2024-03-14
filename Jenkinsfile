node('built-in') {
    stage('continuous intgration_master'){
    git 'https://github.com/srinath111/maven1.git'
    }
    stage('continuous build_master'){
        sh 'mvn package'
    }
    stage('continuous devlivery_master'){
        deploy adapters: [tomcat9(credentialsId: 'dac6c3c8-4e2a-4a72-a378-0cdf72041db0', path: '', url: 'http://10.1.4.81:8080')], contextPath: 'sri1t', war: '**/*.war'
    }
    stage('continuous testing_master'){
        git 'https://github.com/srikorboina/sr.git'
        sh 'java -jar /root/.jenkins/workspace/srinath_master/testing.jar'
    }
    stage('continuous deploy_master'){
        input message: 'please approve', submitter: 'sri'
        deploy adapters: [tomcat9(credentialsId: 'dac6c3c8-4e2a-4a72-a378-0cdf72041db0', path: '', url: 'http://10.1.2.222:8080')], contextPath: 'prod1', war: '**/*.war'
    }
}

