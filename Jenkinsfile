node {    
      stage('SCM Checkout') {
             git credentialsId: 'git_credentials', url: 'https://github.com/francis0516/hello-world-war.git'
      }   
      stage('Build') {     
             // Get Maven Home Path
             def mvnHome = tool name: 'Maven 3', type: 'maven'
             sh "${mvnHome}/bin/mvn package"
             echo "Deploy Tomcat Pipeline Test Passed"
      }
      stage('Test') {
             // Get Maven Home Path
             def mvnHome = tool name: 'Maven 3', type: 'maven'
             sh "${mvnHome}/bin/mvn package"
      }
      stage('Deploy war file'){
             def mvnHome = tool name: 'Maven 3', type: 'maven'
             sh "scp /var/lib/jenkins/workspace/Deploy_Tomcat_Pipeline/target/hello-world-war-1.0.0.war root@192.168.1.13:/opt/apache-tomcat-9.0.17/webapps"
      }
}
