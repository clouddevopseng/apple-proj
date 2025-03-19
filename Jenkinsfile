node {
    stage('Download') 
    {
    git branch: 'dev', url: 'https://github.com/clouddevopseng/apple-proj.git'
    }
    stage('Covert into artifacts') 
    {
    sh 'mvn package'
    }
    stage('Deployment') 
    {
    deploy adapters: [tomcat9(credentialsId: 'id', path: '', url: 'http://172.31.7.102:8080/')], contextPath: '/groovy-script', war: '**/*.war'
    }
}
