node('built-in') {
    stage('continuous intgration_master'){
    git 'https://github.com/srinath111/raju.git'
    }
    stage('continuous build_master'){
        sh 'mvn package'
    }
    stage('continuous devlivery_master'){
        deploy adapters: [tomcat9(credentialsId: 'db8b7ed0-501d-4d83-b874-6b42ce600110', path: '', url: 'http://10.1.4.81:8080')], contextPath: 'test1app', war: '**/*.war'
    }
    stage('continuous testing_master'){
        git 'https://github.com/srikorboina/sr.git'
        sh 'java -jar /root/.jenkins/workspace/srinath/testing.jar'
    }
    stage('continuous deploy_master'){
        input message: 'please approve', submitter: 'sri'
        deploy adapters: [tomcat9(credentialsId: 'db8b7ed0-501d-4d83-b874-6b42ce600110', path: '', url: 'http://10.1.2.222:8080')], contextPath: 'sri1app', war: '**/*.war'
    }
}

