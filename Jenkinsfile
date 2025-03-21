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
    deploy adapters: [tomcat9(credentialsId: 'id', path: '', url: 'http://172.31.7.102:8080/')], contextPath: '/dev-env-new', war: '**/*.war'
    }
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
    deploy adapters: [tomcat9(credentialsId: 'id', path: '', url: 'http://172.31.7.102:8080/')], contextPath: '/dev-env-new', war: '**/*.war'
    }
	post {
	  success {
	     emailext(
		   to: harishgoud0606@gmail.com,growupskills100@gmail.com,
		   subject: "Buil Successfully executed",
		   body: "The Build Success"
		   )
		 }
	  failure{
	     emailext(
		   to: harishgoud0606@gmail.com,growupskills100@gmail.com,
		   subject: "Failed",
		   body: "Look into this"
		   )
		 }
	  }
}
}
