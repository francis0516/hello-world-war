node {    
      stage('SCM Checkout') {
             git 'https://github.com/francis0516/hello-world-war'
      }   
      stage('Build') {     
             // Get Maven Home Path
             def mvnHome = tool name: 'Maven 3', type: 'maven'
             sh "${mvnHome}/bin/mvn package"
             echo "Verizon Test Passed"
      }
      stage('Test'){
             // Get Maven Home Path
             def mvnHome = tool name: 'Maven 3', type: 'maven'
             sh "${mvnHome}/bin/mvn package"
      }
      stage('Deploy war file'){
             def mvnHome = tool name: 'Maven 3', type: 'maven'
             sh "scp /var/lib/jenkins/workspace/VerizonApp/target/hello-world-war-1.0.0.war root@192.168.1.13:/opt/apache-tomcat-9.0.17/webapps"
      }
}
