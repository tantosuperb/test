

def mvnBuild(testType)
    stage('build') {
        withEnv(["PATH+MAVEN=${tool 'mvn-3.6.0'}/bin"]) {
            sh 'mvn --version'
            sh "mvn clean ${testType}"
        }
    }
    
    stage('report') {
        junit 'target/surefire-reports/*.xml'
        jacoco execPattern: 'target/**.exec'
    }
}
