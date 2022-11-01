node('built-in')
{
    stage('continousdownload') 
    {
       git 'https://github.com/ashokkumar325/mymaven.git'
    }
    stage('continousbuild') 
    {
       sh 'mvn package' 
    }
    stage('continousdeploye') 
    {
        deploy adapters: [tomcat9(credentialsId: 'f37ebbb1-3e49-4358-b506-0aa10ce3230b', path: '', url: 'http://172.31.19.182:8080')], contextPath: 'testapp', war: '**/*.war'
    }
    stage('continoustesting') 
    {
       git '  https://github.com/intelliqittrainings/FunctionalTesting.git'
       sh 'java -jar /var/lib/jenkins/workspace/scripeted_pipeline1/testing.jar'
    }
    stage('continousDeliver') 
    {
        deploy adapters: [tomcat9(credentialsId: 'f37ebbb1-3e49-4358-b506-0aa10ce3230b', path: '', url: 'http://172.31.16.152:8080')], contextPath: 'myapp', war: '**/*.war'
    }
}
    
