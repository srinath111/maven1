node('built-in') {
    stage('continuous intgration'){
    git 'https://github.com/srinath111/raju.git'
    }
    stage('continuous build'){
        sh 'mvn package'
    }
    stage('continuous devlivery'){
        deploy adapters: [tomcat9(credentialsId: 'db8b7ed0-501d-4d83-b874-6b42ce600110', path: '', url: 'http://10.1.4.81:8080')], contextPath: 'testapp', war: '**/*.war'
    }
    stage('continuous testing'){
        git 'https://github.com/srikorboina/sr.git'
        sh 'java -jar /root/.jenkins/workspace/script/testing.jar'
    }
    stage('continuous deploy'){
        input message: 'please approve', submitter: 'sri'
        deploy adapters: [tomcat9(credentialsId: 'db8b7ed0-501d-4d83-b874-6b42ce600110', path: '', url: 'http://10.1.2.222:8080')], contextPath: 'sriapp', war: '**/*.war'
    }
}

