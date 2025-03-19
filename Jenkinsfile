node {
    stage('Download') 
    {
    git branch: 'release', url: 'https://github.com/clouddevopseng/apple-proj.git'
    }
    stage('Covert into artifacts') 
    {
    sh 'mvn package'
    }
    stage('Deployment') 
    {
    deploy adapters: [tomcat9(credentialsId: 'id', path: '', url: 'http://172.31.7.145:8080')], contextPath: '/release-env', war: '**/*.war'
    }
}
